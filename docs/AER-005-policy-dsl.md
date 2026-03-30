# AER-005: Policy DSL (Policy Definition Language)

**Status:** Draft
**Version:** 0.1
**Depends on:** AER-001, AER-002, AER-004
**Category:** Execution Policy / Enforcement

---

## 1. Abstract

Defines a **declarative language** for expressing policies applied to Artificial Entities.

Goals:
- Machine-readable
- Human-readable
- Enforceable at runtime

---

## 2. Design Principles

- Declarative over imperative
- Deterministic evaluation
- Composable rules
- Runtime-safe

---

## 3. Basic Syntax

```yaml
policy:
  name: "no-harm-policy"
  applies_to: "*"

rules:
  - condition: action.type == "execute_trade"
    if: amount > 10000
    then: require_approval

  - condition: data.sensitivity == "high"
    then: deny
```

---

## 4. Rule Structure

```yaml
- condition: <expression>
  then: <action>
```

Optional:
```yaml
  else: <action>
```

---

## 5. Supported Actions

| Action | Description |
|--------|-------------|
| allow | Permit execution |
| deny | Block execution |
| require_approval | Human approval needed |
| restrict | Reduce capabilities |
| isolate | Sandbox execution |
| terminate | Kill agent |

---

## 6. Conditions

Expressions support:

```
action.type
input.data
user.role
risk.level
agent.capabilities
time.now
```

Example:
```yaml
condition: user.role != "admin" && action.type == "delete"
then: deny
```

---

## 7. Composition

```yaml
policy:
  extends: "base-policy"

rules:
  - condition: risk.level == "high"
    then: isolate
```

---

## 8. Priority

Rules evaluated top-down.

Optional priority:
```yaml
priority: 100
```

---

## 9. Runtime Hooks

Policy engine MUST support:
- pre_execution
- mid_execution
- post_execution

---

## 10. Example (Realistic)

```yaml
policy:
  name: "trading-agent-policy"

rules:
  - condition: action.type == "trade" && amount > 1000
    then: require_approval

  - condition: risk.level == "critical"
    then: terminate

  - condition: agent.constraint == "no_external_calls"
    then: deny
```

---

## 11. Enforcement Mapping

Policy → REP (AER-002):
- deny → block in PEC
- isolate → RTM sandbox
- terminate → kill switch

---

## 12. Safety Guarantees

Policy engine:
- MUST be deterministic
- MUST NOT be modifiable by AE
- MUST run outside AE execution context

---

## 13. Future Extensions

- Policy signing
- Distributed policy sync
- AI-generated policies (with validation)
- Formal verification
