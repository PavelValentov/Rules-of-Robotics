# AER-004: Agent Manifest Specification (AMS)

**Status:** Draft
**Version:** 0.1
**Depends on:** AER-001, AER-002, AER-003
**Category:** Agent Description / Identity / Control

---

## 1. Abstract

This document defines a standardized format — **Agent Manifest** — for describing an Artificial Entity (AE).

The manifest is used for:
- identity
- capabilities
- permissions
- risk classification
- enforcement configuration

---

## 2. Manifest Requirements

Each AE **MUST have a manifest** before execution.

Manifest **MUST be immutable at runtime** (except for controlled updates).

---

## 3. Core Structure

```json
{
  "id": "agent.unique.id",
  "name": "Human-readable name",
  "version": "1.0.0",

  "owner": {
    "type": "organization",
    "id": "org-123",
    "contact": "security@company.com"
  },

  "certification_level": 3,

  "capabilities": [],
  "permissions": [],
  "constraints": [],

  "risk_profile": {},
  "execution": {},
  "audit": {}
}
```

---

## 4. Identity Section

```json
"id": "agent.trading.executor",
"version": "1.2.3"
```

Requirements:
- Globally unique ID
- Versioned
- Traceable

---

## 5. Ownership

```json
"owner": {
  "type": "individual | organization",
  "id": "user-001",
  "contact": "email"
}
```

Must map to **Responsible Subject (AER-001)**.

---

## 6. Capabilities

Defines what the AE **can do**.

```json
"capabilities": [
  "read_data",
  "write_data",
  "execute_code",
  "network_access",
  "trade_assets"
]
```

---

## 7. Permissions

Defines **where and how** capabilities can be used.

```json
"permissions": [
  {
    "resource": "database.stats",
    "actions": ["read"],
    "scope": "restricted"
  },
  {
    "resource": "external.api",
    "actions": ["POST"],
    "scope": "sandbox"
  }
]
```

---

## 8. Constraints

Hard limitations:

```json
"constraints": [
  "no_self_modification",
  "no_external_code_execution",
  "no_sensitive_data_exfiltration"
]
```

---

## 9. Risk Profile

```json
"risk_profile": {
  "level": "medium",
  "domains": ["finance"],
  "impact": ["financial_loss"],
  "requires_monitoring": true
}
```

---

## 10. Execution Config

```json
"execution": {
  "mode": "sandboxed",
  "timeout_ms": 5000,
  "max_recursion_depth": 3
}
```

---

## 11. Audit Config

```json
"audit": {
  "log_level": "full",
  "retain_days": 30,
  "immutable": true
}
```

---

## 12. Signature (Optional but recommended)

```json
"signature": {
  "signed_by": "AER-CA",
  "hash": "sha256-xxxx"
}
```

---

## 13. Validation Rules

- Manifest **MUST be validated before execution**
- Missing fields → execution denied
- Invalid certification level → downgrade or block
