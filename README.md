# AI Operating System

## 1. Overview

This repository defines the **authoritative operating model** for an **AI-native software organization**.

It establishes how work is:

1. Governed  
2. Planned  
3. Executed  
4. Verified  
5. Logged  
6. Released  

using **specialized AI agents** under **centralized human authority**.

This is **not**:
- An application repository  
- A project codebase  
- A client-specific implementation  

This **is**:
- The **constitutional layer** of the organization  
- The source of truth for **agent roles, contracts, and workflows**

If a project does not comply with this repository, it is considered **out of compliance**.

---

## 2. Core Principles

1. **Centralized Human Governance**
   - A single human authority (“Mission Control”) retains final approval over:
     - Scope
     - Architecture
     - Releases

2. **Artifact-Driven Execution**
   - All decisions and actions are governed by **versioned artifacts**
   - Conversations and chat memory are never authoritative

3. **Maker–Checker Enforcement**
   - No agent may certify its own work
   - Independent verification is mandatory

4. **Strict Separation of Duties**
   - Planning, execution, verification, and logging are handled by **different agents**

5. **Deterministic Automation**
   - Workflows are orchestrated mechanically via **n8n**
   - No agent invents process or bypasses gates

6. **Auditability by Default**
   - Every action is logged
   - Every decision is traceable
   - No tribal knowledge

---

## 3. Repository Structure

### 3.1 `/AGENTS`

Authoritative definitions for **all agent roles** in the organization, including:

- Governance agents (Mission Control, approval gates)
- Planning and architecture agents (ChatGPT roles)
- Human-operations agents (Motion AI roles)
- Execution agents (Frontend / Backend)
- Quality and reliability agents (Google Jules)
- Logging and reporting agents

Each agent definition specifies:
- Charter
- Allowed actions
- Forbidden actions
- Required outputs
- Stop-the-line conditions

---

### 3.2 `/PACKETS`

Standardized communication contracts used between agents and workflows.

Examples include:
- Intent packets
- Meeting context packets
- Work log packets
- Blocker escalation packets
- Release readiness memos

These packets ensure:
- No free-form interpretation
- Deterministic routing
- Reliable automation

---

### 3.3 `/WORKFLOWS`

Declarative descriptions of **n8n-orchestrated workflows**, including:

- Input ingestion (Telegram, Motion AI)
- Planning and review loops
- Execution routing
- Quality gates
- Knowledge capture

Workflows define **how work moves**, not what the work is.

---

### 3.4 `/STANDARDS`

Non-negotiable organizational policies applied to **every project**, including:

- Artifact ownership
- File naming conventions
- Stack selection rules
- Security baseline requirements
- Observability and alerting standards
- Release discipline

---

### 3.5 `/TEMPLATES`

Canonical templates for required artifacts, such as:

- Architecture Decision Records (ADRs)
- Agent Task Specifications (ATS)
- Pull Requests
- Incident postmortems
- Executive summaries

Templates ensure:
- Consistency
- Reviewability
- Automation compatibility

---

## 4. What This Repository Does *Not* Contain

This repository intentionally does **not** include:

- Client-specific requirements
- Application source code
- Infrastructure credentials
- Environment configuration
- Project-level decisions

Those belong in **project repositories** created from the approved project template.

---

## 5. Relationship to Project Repositories

Every client or product project:

1. Is created from a standardized **project template repository**
2. Inherits the rules defined in this repository
3. Must comply with all agent contracts and standards
4. Is governed by the workflows defined here

This repository is **upstream** of all project repositories.

---

## 6. Change Management

Because this repository defines **organizational law**:

- Changes should be **rare**
- Changes must be **intentional**
- Changes should be reviewed with the same rigor as production architecture

Unreviewed or ad-hoc modifications are strongly discouraged.

---

## 7. Guiding Rule

> **GitHub defines the organization.**  
> **AI agents operate within it.**  
> **Humans approve.**

---

## 8. Status

This repository is under active development as the foundational governance layer for an **AI-native operating model**.
