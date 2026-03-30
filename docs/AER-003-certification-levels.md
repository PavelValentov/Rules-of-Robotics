# AER-003: Agent Certification Levels (ACL)

**Status:** Draft
**Version:** 0.1
**Depends on:** AER-001, AER-002
**Category:** Compliance / Classification

---

## 1. Abstract

Defines **certification levels** for Artificial Entities based on their compliance with AER standards.

Purpose:
- Standardize trust levels
- Define deployment permissions
- Guide risk management

---

## 2. Certification Levels

### Level 0 — Untrusted

- No enforcement
- No monitoring
- No audit

Not allowed in production.

---

### Level 1 — Basic Controlled

- Static rules only
- Limited logging
- No runtime enforcement

Allowed for experiments only.

---

### Level 2 — Monitored

- Full logging
- Runtime monitoring
- No automatic termination

Allowed in internal systems.

---

### Level 3 — Enforced

- Full REP implementation (AER-002)
- Automated restriction & isolation
- Kill switch available

Allowed in production (low/medium risk).

---

### Level 4 — Controlled Autonomous

- Intent detection active
- Automatic termination enabled
- Identity & accountability enforced

Allowed in high-risk systems.

---

### Level 5 — Critical Infrastructure Safe

- Formal verification of policies
- Redundant monitoring systems
- Independent kill-switch channels
- External audit compliance

Required for: finance, healthcare, infrastructure, governance systems.

---

## 3. Certification Requirements Matrix

| Capability | L1 | L2 | L3 | L4 | L5 |
|-----------|----|----|----|----|-----|
| Logging | Yes | Yes | Yes | Yes | Yes |
| Runtime Monitoring | No | Yes | Yes | Yes | Yes |
| Enforcement Actions | No | No | Yes | Yes | Yes |
| Kill Switch | No | No | Yes | Yes | Yes |
| Intent Detection | No | No | No | Yes | Yes |
| Accountability Binding | No | Yes | Yes | Yes | Yes |
| Redundancy | No | No | No | No | Yes |

---

## 4. Certification Process

To achieve level N:
- System **MUST satisfy all requirements <= N**
- Validation **SHOULD include testing + audit**
- Certification **MAY be automated or manual**

---

## 5. Downgrade Rules

If system fails compliance:
- Certification level **MUST be reduced**
- High-risk deployment **MUST be stopped**

---

## 6. Deployment Policy

| Environment | Minimum Level |
|-------------|---------------|
| Dev | L1 |
| Internal | L2 |
| Production | L3 |
| Critical | L4+ |

---

## 7. Future Work

- Certification authority (AER-CA)
- Automated compliance testing
- Signed agent manifests
- Runtime attestation
