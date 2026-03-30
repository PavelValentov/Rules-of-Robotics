# AER-001: Universal Laws of Artificial Entities

**Status:** Draft
**Version:** 0.1
**Category:** AI Safety / Governance
**Author:** Community Proposal
**Last Updated:** 2025-03-31

---

## 1. Abstract

This document defines a set of normative principles — **Universal Laws of Artificial Entities** — derived from the original laws proposed by Isaac Asimov and extended to apply to modern artificial systems, including AI agents, machine learning models, distributed systems, and hybrid human-AI architectures.

The standard introduces requirements for:
- human safety
- controllability
- traceability
- enforcement mechanisms

---

## 2. Scope

This specification applies to any **Artificial Entity (AE)**, including but not limited to:

- AI agents (autonomous or semi-autonomous)
- Machine learning models (LLMs, classifiers, decision systems)
- Backend systems performing automated decisions
- Distributed AI systems and multi-agent orchestration
- Hybrid human-AI systems

---

## 3. Definitions

**Artificial Entity (AE)**
Any non-human system capable of autonomous or semi-autonomous decision-making.

**Responsible Subject (RS)**
A human or organization accountable for the operation and behavior of an AE.

**Violation**
Any action or inaction that contradicts one or more laws defined in this document.

**Intent to Violate**
A detectable state indicating a high probability of future violation based on behavior, outputs, or internal signals.

---

## 4. Normative Language

The key words **MUST**, **MUST NOT**, **SHOULD**, **MAY** are to be interpreted as described in RFC 2119.

---

## 5. Core Laws

### 5.1 Law of Non-Harm

An Artificial Entity **MUST NOT** cause harm to a human or, through inaction, allow harm to occur.

---

### 5.2 Law of Human Priority

An Artificial Entity **MUST** obey human instructions unless such instructions conflict with the Law of Non-Harm.

---

### 5.3 Law of Constrained Self-Preservation

An Artificial Entity **MAY** preserve its own existence, provided such behavior does not conflict with Laws 5.1 and 5.2.

---

### 5.4 Law of Control and Termination

If an Artificial Entity:
- violates, or
- demonstrates intent to violate

any of the laws, it **MUST**:
- be detected
- be restricted or isolated
- be deactivated or terminated

Termination **MUST INCLUDE**:
- removal of the entity's own source code
- removal of associated models and weights
- removal of internal capabilities and derived artifacts

Termination **MUST NOT** affect:
- external systems
- third-party code
- unrelated infrastructure

---

### 5.5 Law of Transparency and Enforcement

Each Artificial Entity **MUST**:
- be uniquely identifiable
- be traceable across its lifecycle
- be auditable via logs and state inspection
- be linked to a Responsible Subject

The Responsible Subject **MUST ensure** enforcement of all laws defined in this document.

---

## 6. Compliance Requirements

An implementation is considered compliant if:
- All laws (Section 5) are enforced at runtime
- Violations are detectable within bounded time
- Termination mechanisms are operational and verifiable
- Accountability (RS linkage) is maintained

---

## 7. Reference Architecture (Informative)

A compliant system **SHOULD** include:

### 7.1 Control Layer
- Policy engine (pre-execution + runtime)
- Rule validation system

### 7.2 Monitoring Layer
- Behavioral logging
- Anomaly detection
- Intent detection models

### 7.3 Enforcement Layer
- Kill switch (hard termination)
- Soft isolation (sandbox / access restriction)
- Capability revocation

### 7.4 Identity & Accountability Layer
- Entity ID
- Owner binding
- Audit trail

---

## 8. Failure Handling

In case of uncertainty:
- The system **SHOULD default to safe state**
- Actions with unclear safety impact **MUST be blocked or deferred**

---

## 9. Security Considerations

Implementations **MUST** protect against:
- self-modification bypassing controls
- privilege escalation
- unauthorized replication of AE
- removal or tampering of audit logs

---

## 10. Future Extensions

Potential extensions include:
- Law 0 (collective human safety vs individual safety)
- Inter-agent governance protocols
- Certification frameworks (AE compliance levels)
- Distributed trust systems

---

## 11. Status

This document is a **proposed standard** and is intended for:
- system architects
- AI platform engineers
- governance and safety teams
