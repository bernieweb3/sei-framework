# Truth Layer Specification

> Defining the authoritative sources of data and system state in Spatial Experience Interfaces.

---

## Truth Layer Overview

### Definition

The Truth Layer is the authoritative source of all data and system state. It consists of all backend systems, APIs, databases, smart contracts, and external services that provide the actual data displayed in the Experience Layer.

### Core Principle

```
The Experience Layer must never fabricate truth.
It must only represent the Truth Layer.
```

---

## Truth Layer Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    EXPERIENCE LAYER                      │
│  (Environment, Objects, Hotspots, Overlays, Visuals)    │
└─────────────────────────┬───────────────────────────────┘
                          │
                          │ Reads / Writes
                          ▼
┌─────────────────────────────────────────────────────────┐
│                      TRUTH LAYER                         │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐     │
│  │   APIs      │  │  Database   │  │  Blockchain │     │
│  │             │  │             │  │  Contracts  │     │
│  └─────────────┘  └─────────────┘  └─────────────┘     │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐     │
│  │  External   │  │   Auth      │  │   Cache     │     │
│  │  Services   │  │  Service    │  │   Layer     │     │
│  └─────────────┘  └─────────────┘  └─────────────┘     │
└─────────────────────────────────────────────────────────┘
```

---

## Data Source Inventory

### Complete Source Registry

| Source ID | Source Name | Type | Purpose | Auth Required? |
|-----------|-------------|------|---------|----------------|
| SRC-001 | [Name] | [Type] | [Purpose] | [Yes/No] |
| SRC-002 | [Name] | [Type] | [Purpose] | [Yes/No] |
| SRC-003 | [Name] | [Type] | [Purpose] | [Yes/No] |

---

## Data Source Types

### API Endpoints

**Characteristics:**
- RESTful or GraphQL
- JSON data format
- Request/response pattern

**Use for:** Dynamic data, user-specific data, computed values

**Example:**
```yaml
Source Type: REST API
Base URL: https://api.example.com/v1
Endpoints:
  - GET /user/balance
  - POST /transactions/deposit
  - GET /analytics/metrics
```

---

### Smart Contracts

**Characteristics:**
- On-chain data
- Immutable records
- Transaction-based updates

**Use for:** Financial data, ownership records, decentralized state

**Example:**
```yaml
Source Type: Smart Contract
Network: [Ethereum/Polygon/Solana/etc]
Contract Address: [0x...]
ABI: [Contract ABI reference]
Methods:
  - balanceOf(address)
  - deposit(uint256)
  - withdraw(uint256)
```

---

### Database

**Characteristics:**
- Structured storage
- Fast queries
- CRUD operations

**Use for:** User profiles, application state, cached data

**Example:**
```yaml
Source Type: Database
Type: [PostgreSQL/MongoDB/etc]
Connection: [Connection string]
Tables/Collections:
  - users
  - transactions
  - settings
```

---

### External Services

**Characteristics:**
- Third-party APIs
- Specialized functionality
- Rate limits apply

**Use for:** Analytics, notifications, search, content

**Example:**
```yaml
Source Type: External API
Service: [Service name]
Base URL: [URL]
Authentication: [API Key/OAuth]
Endpoints:
  - GET /search
  - POST /notify
```

---

## Data Mapping

### UI Data to Source Mapping

Map every data field in the UI to its authoritative source:

| UI Field | Display Location | Source | Source Type | Update Frequency |
|----------|------------------|--------|-------------|------------------|
| [Field 1] | [Overlay/Zone] | [Source] | [Type] | [Frequency] |
| [Field 2] | [Overlay/Zone] | [Source] | [Type] | [Frequency] |
| [Field 3] | [Overlay/Zone] | [Source] | [Type] | [Frequency] |

### Example Mapping

| UI Field | Display Location | Source | Source Type | Update Frequency |
|----------|------------------|--------|-------------|------------------|
| User Balance | Vault Overlay | Smart Contract | on-chain | Real-time (WebSocket) |
| Deposit APY | Vault Overlay | Backend API | API | Every 5 minutes |
| Transaction History | Vault Overlay | Subgraph | indexed | On load |
| User Level | Progression Zone | Database | API | On level up |
| Leaderboard | Stats Overlay | Backend API | API | Every 10 minutes |

---

## State Synchronization

### Synchronization Strategies

| Strategy | Use Case | Implementation |
|----------|----------|----------------|
| Polling | Simple, infrequent updates | SetInterval with API calls |
| WebSocket | Real-time updates | Persistent connection |
| Server-Sent Events | Server-push updates | EventSource API |
| Manual Refresh | User-triggered updates | Refresh button/action |
| Subscription | GraphQL subscriptions | ws-based subscriptions |

### Synchronization Configuration

```yaml
Data Field: User Balance
Source: Smart Contract
Strategy: WebSocket
Update Trigger:
  - On overlay open
  - On transaction completion
  - On WebSocket event
Fallback: Polling every 30 seconds
```

---

## Data Validation Rules

### Client-Side Validation

Validate data before sending to Truth Layer:

| Field | Validation Rules | Error Message |
|-------|------------------|---------------|
| [Field 1] | [Rules] | [Message] |
| [Field 2] | [Rules] | [Message] |

### Server-Side Validation

Truth Layer must validate all incoming data:

```yaml
Endpoint: POST /deposit
Validations:
  - Amount > 0
  - Amount <= user.balance
  - User is authenticated
  - Rate limit not exceeded
```

---

## Error Handling

### Error Categories

| Category | Description | User Message |
|----------|-------------|--------------|
| Network | Connection failed | "Please check your connection" |
| Validation | Invalid input | "Please check your input" |
| Authorization | Not authorized | "Please connect your wallet" |
| Server | Server error | "Something went wrong. Please try again." |
| Contract | Transaction failed | "Transaction failed. [Details]" |

### Error Response Format

```json
{
  "error": {
    "code": "ERROR_CODE",
    "message": "Human-readable message",
    "details": {},
    "action": "suggested user action"
  }
}
```

---

## Caching Strategy

### Cache Layers

| Layer | Purpose | TTL |
|-------|---------|-----|
| Browser Cache | Static assets | 1 hour |
| API Cache | API responses | 5 minutes |
| State Cache | Application state | Session |

### Cache Invalidation

| Data Type | Invalidation Trigger |
|-----------|---------------------|
| User balance | Transaction completion |
| Leaderboard | New entry added |
| Settings | User update |

---

## Security Considerations

### Authentication

| Method | Use Case | Implementation |
|--------|----------|----------------|
| JWT | API authentication | Bearer token in header |
| Wallet Signature | Web3 authentication | Sign message with wallet |
| API Key | External services | Key in header |

### Authorization

| Resource | Required Permission |
|----------|-------------------|
| User data | User must be owner |
| Admin functions | Admin role required |
| Write operations | Authenticated user |

### Data Protection

- Sensitive data encrypted in transit (HTTPS)
- Sensitive data encrypted at rest
- No secrets in client-side code

---

## Mock Data Policy

### Development Phase

```
Mock data is ALLOWED during development.
Must be clearly labeled as mock data.
Must be replaced before deployment.
```

### Production Phase

```
Mock data is FORBIDDEN in production.
All data must come from Truth Layer.
No simulated values.
No placeholder data.
```

### Mock Data Checklist

- [ ] All mock data sources identified
- [ ] Replacement plan documented
- [ ] Truth Layer connections tested
- [ ] Mock data removed from production build

---

## Example: Complete Truth Layer Spec

### DeFi Application

**Data Sources:**

| Source ID | Name | Type | Purpose |
|-----------|------|------|---------|
| SRC-001 | Vault Contract | Smart Contract | Balance, deposits, withdrawals |
| SRC-002 | Analytics API | REST API | APY, metrics, history |
| SRC-003 | User Database | PostgreSQL | User profiles, preferences |
| SRC-004 | Notification Service | External | Push notifications |

**Data Mapping:**

| UI Field | Source | Endpoint/Method |
|----------|--------|-----------------|
| Balance | SRC-001 | balanceOf(userAddress) |
| APY | SRC-002 | GET /vault/apy |
| Deposit | SRC-001 | deposit(amount) |
| History | SRC-002 | GET /user/transactions |
| Notifications | SRC-004 | POST /notify |

**Synchronization:**

| Data | Strategy | Frequency |
|------|----------|-----------|
| Balance | WebSocket | Real-time |
| APY | Polling | 5 minutes |
| History | Manual | On overlay open |

---

## Validation Checklist

- [ ] All data sources identified
- [ ] Every UI field mapped to source
- [ ] Update frequencies defined
- [ ] Synchronization strategy chosen
- [ ] Error handling documented
- [ ] Validation rules specified
- [ ] Security measures in place
- [ ] Mock data replacement plan ready

---

> **Template Version:** SEI v1.0
