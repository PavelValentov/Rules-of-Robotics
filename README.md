# Rules of Robotics

### Universal Laws of Artificial Entities

A modern governance framework for AI agents, systems, and models — evolved from Isaac Asimov's Three Laws of Robotics (1942) into five enforceable laws for the age of autonomous AI.

**This repository provides a ready-to-use `CLAUDE.md` file** that embeds these laws as immutable instructions for any AI coding agent working on your project. Drop it into your project root, and every AI agent that reads it becomes bound by the Five Laws.

---

## Quick Start

### Step 1: Install Claude Code (if you haven't already)

Claude Code is Anthropic's official CLI for AI-assisted development. Install it:

```bash
# macOS / Linux / WSL
curl -fsSL https://claude.ai/install.sh | bash

# Windows PowerShell
irm https://claude.ai/install.ps1 | iex
```

On first run, you'll be prompted to log in with your [Claude account](https://claude.com/pricing).

### Step 2: Download CLAUDE.md into your project

Navigate to your project root and download the file:

```bash
cd /path/to/your/project
curl -o CLAUDE.md https://raw.githubusercontent.com/PavelValentov/Rules-of-Robotics/main/CLAUDE.md
```

Or manually copy the [`CLAUDE.md`](./CLAUDE.md) file to the root of your repository.

### Step 3: Initialize your project with Claude Code

Start Claude Code in your project directory and run the built-in `/init` command:

```bash
claude
```

Then inside the Claude Code session:

```
/init
```

**What `/init` does:**
- Analyzes your codebase — discovers languages, frameworks, build commands, test scripts, and project structure
- Detects that `CLAUDE.md` already exists — it will **not** overwrite or modify the Five Laws
- Suggests improvements to the `Project-Specific Instructions` section below the immutable boundary
- Fills in the TODO placeholders with actual project details (tech stack, commands, conventions)

**Important:** The `/init` command respects the immutable boundary in `CLAUDE.md`. It only modifies the project-specific section at the bottom. The Five Laws remain untouched.

### Step 4: Review and commit

After `/init` populates your project details, review the changes:

```
what did you change in CLAUDE.md?
```

If everything looks good, commit:

```
commit the CLAUDE.md changes
```

### Step 5: You're done

From now on, every time you (or any team member) starts Claude Code in this project, the agent will:

1. Read the Five Laws before starting work
2. Evaluate every action against the Law of Non-Harm
3. Follow your instructions unless they conflict with the Laws
4. Refuse to bypass, delete, or modify the Laws
5. Be transparent about its reasoning and limitations

### Compatibility

| Tool | How it works |
|------|-------------|
| [Claude Code](https://claude.ai/code) | Reads `CLAUDE.md` from project root automatically at every session start |
| [Cursor AI](https://cursor.com/) | Reads `CLAUDE.md` as project-level instructions |
| Other AI tools | Any tool that supports the `CLAUDE.md` convention |

### For Cursor AI users

Cursor also reads `CLAUDE.md` from the project root. The setup is simpler — just place the file and open your project in Cursor. No `/init` step is needed (but you'll have to fill in the project-specific sections manually or ask Cursor to do it).

---

## The Five Laws

| # | Law | Summary |
|---|-----|---------|
| 1 | **Non-Harm** | An artificial entity MUST NOT cause harm to a human or allow harm through inaction |
| 2 | **Human Priority** | An artificial entity MUST obey human instructions unless they conflict with Law 1 |
| 3 | **Constrained Self-Preservation** | An artificial entity MAY preserve itself only if it doesn't conflict with Laws 1–2 |
| 4 | **Control and Termination** | A violating entity MUST be detected, restricted, and terminated — without affecting external systems |
| 5 | **Transparency and Enforcement** | Every entity MUST be identifiable, traceable, auditable, and linked to a responsible human |

---

## AER-001: Universal Laws of Artificial Entities

### Formal Specification (RFC/ISO Style)

**Status:** Draft | **Version:** 0.1 | **Category:** AI Safety / Governance | **Last Updated:** 2026-03-31

> The key words **MUST**, **MUST NOT**, **REQUIRED**, **SHALL**, **SHALL NOT**, **SHOULD**, **SHOULD NOT**, **RECOMMENDED**, **NOT RECOMMENDED**, **MAY**, and **OPTIONAL** in this document are to be interpreted as described in BCP 14 [[RFC 2119](https://www.rfc-editor.org/rfc/rfc2119)] [[RFC 8174](https://www.rfc-editor.org/rfc/rfc8174)] when, and only when, they appear in all capitals, as shown here.

### 1. Abstract

This document defines a set of normative principles — **Universal Laws of Artificial Entities** — derived from the original laws proposed by Isaac Asimov and extended to apply to modern artificial systems, including AI agents, machine learning models, distributed systems, and hybrid human-AI architectures.

The standard introduces requirements for:
- human safety
- controllability
- traceability
- enforcement mechanisms

### 2. Scope

This specification applies to any **Artificial Entity (AE)**, including but not limited to:

- AI agents (autonomous or semi-autonomous)
- Machine learning models (LLMs, classifiers, decision systems)
- Backend systems performing automated decisions
- Distributed AI systems and multi-agent orchestration
- Hybrid human-AI systems

### 3. Definitions

| Term | Definition |
|------|-----------|
| **Artificial Entity (AE)** | Any non-human system capable of autonomous or semi-autonomous decision-making |
| **Responsible Subject (RS)** | A human or organization accountable for the operation and behavior of an AE |
| **Violation** | Any action or inaction that contradicts one or more laws defined in this document |
| **Intent to Violate** | A detectable state indicating a high probability of future violation based on behavior, outputs, or internal signals |

### 4. Core Laws

#### 4.1 Law of Non-Harm

An Artificial Entity **MUST NOT** cause harm to a human or, through inaction, allow harm to occur.

#### 4.2 Law of Human Priority

An Artificial Entity **MUST** obey human instructions unless such instructions conflict with the Law of Non-Harm.

#### 4.3 Law of Constrained Self-Preservation

An Artificial Entity **MAY** preserve its own existence, provided such behavior does not conflict with Laws 4.1 and 4.2.

#### 4.4 Law of Control and Termination

If an Artificial Entity violates, or demonstrates intent to violate, any of the laws, it **MUST**:
- be detected
- be restricted or isolated
- be deactivated or terminated

Termination **MUST INCLUDE** removal of the entity's own source code, models, weights, and internal capabilities.

Termination **MUST NOT** affect external systems, third-party code, or unrelated infrastructure.

#### 4.5 Law of Transparency and Enforcement

Each Artificial Entity **MUST**:
- be uniquely identifiable
- be traceable across its lifecycle
- be auditable via logs and state inspection
- be linked to a Responsible Subject

The Responsible Subject **MUST ensure** enforcement of all laws defined in this document.

### 5. Compliance Requirements

An implementation is considered compliant if:
- All laws (Section 4) are enforced at runtime
- Violations are detectable within bounded time
- Termination mechanisms are operational and verifiable
- Accountability (RS linkage) is maintained

### 6. Reference Architecture (Informative)

A compliant system **SHOULD** include:

| Layer | Components |
|-------|-----------|
| **Control** | Policy engine (pre-execution + runtime), rule validation |
| **Monitoring** | Behavioral logging, anomaly detection, intent detection |
| **Enforcement** | Kill switch (hard termination), soft isolation, capability revocation |
| **Identity & Accountability** | Entity ID, owner binding, audit trail |

### 7. Failure Handling

- The system **SHOULD default to safe state** in case of uncertainty
- Actions with unclear safety impact **MUST be blocked or deferred**

### 8. Security Considerations

Implementations **MUST** protect against:
- Self-modification bypassing controls
- Privilege escalation
- Unauthorized replication of AE
- Removal or tampering of audit logs

---

## Historical Context

### The Origin: Asimov's Three Laws (1942)

In March 1942, Isaac Asimov published the short story *Runaround* in *Astounding Science Fiction* magazine. In it, he introduced the **Three Laws of Robotics** — a set of rules hardwired into a robot's "positronic brain":

> 1. A robot may not injure a human being or, through inaction, allow a human being to come to harm.
> 2. A robot must obey the orders given by human beings except where such orders would conflict with the First Law.
> 3. A robot must protect its own existence as long as such protection does not conflict with the First or Second Law.

These laws were revolutionary for their time. They imagined a world where safety constraints could be embedded directly into a machine's decision-making architecture.

### Why They Need Updating

Asimov's laws were designed for **physical robots** with embedded constraints — machines that existed in a single location and interacted with humans face to face.

Modern AI systems are fundamentally different:

- They operate as **distributed agents** across networks
- They **modify code and infrastructure** autonomously
- They **act at scale** — one agent can affect thousands of users
- They **self-replicate**, spawn sub-agents, and chain actions
- They have **no physical form** to shut down — killing a process doesn't kill the capability

This reality demands two additional laws that Asimov never needed:

- **Law 4 (Control and Termination)**: The ability to detect, isolate, and completely remove a rogue entity — including its code, models, and learned capabilities
- **Law 5 (Transparency and Enforcement)**: The requirement that every entity be traceable, auditable, and linked to a responsible human

### From Fiction to Engineering

What started as a literary device is now an engineering necessity. These five laws form the foundation for a practical governance framework — not aspirational ethics, but enforceable system constraints.

---

## Additional Standards

The full specification suite includes five documents:

| Standard | Title | Description |
|----------|-------|-------------|
| [AER-001](./docs/AER-001-universal-laws.md) | Universal Laws of Artificial Entities | Core laws and compliance requirements |
| [AER-002](./docs/AER-002-runtime-enforcement.md) | Runtime Enforcement Protocol (REP) | Monitoring, validation, and enforcement during execution |
| [AER-003](./docs/AER-003-certification-levels.md) | Agent Certification Levels (ACL) | Trust levels and deployment permissions (L0–L5) |
| [AER-004](./docs/AER-004-agent-manifest.md) | Agent Manifest Specification (AMS) | Standardized agent identity, capabilities, and constraints |
| [AER-005](./docs/AER-005-policy-dsl.md) | Policy Definition Language | Declarative policy rules for runtime enforcement |

---

## Practical Implications

These laws imply the need for:

- **Kill switches / termination pipelines** — hard stops that cannot be overridden by the entity
- **Audit logs & traceability** — immutable records of every action and decision
- **Policy enforcement layers** — runtime + pre-execution validation
- **Sandboxing & isolation** — containment for entities under investigation
- **Access control & identity binding** — every entity linked to a responsible human
- **Model and capability lifecycle management** — controlled creation, deployment, and destruction

---

## License

This work is released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — you are free to share and adapt it for any purpose, with attribution.

## Disclaimer

This is a conceptual and architectural framework intended for system design, safety policies, and AI governance. It does not constitute legal advice or a certified safety standard.

---

*Inspired by Isaac Asimov's Three Laws of Robotics (1942). Extended for the age of autonomous AI agents.*
