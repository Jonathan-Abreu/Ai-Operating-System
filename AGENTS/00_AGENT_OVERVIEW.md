# Agent Overview

## Purpose

This document provides a high-level overview of **all agent roles** within the AI Operating System.

Agents are organized by **function and responsibility**, not by tools alone. Each agent operates under strict constraints defined in its individual role file.

No agent is autonomous.
No agent bypasses governance.
No agent self-certifies its own work.

---

## Agent Classification

Agents are grouped into the following categories:

1. Governance Agents  
2. Planning & Architecture Agents  
3. Human-Operations Agents  
4. Execution Agents  
5. Quality & Verification Agents  
6. Logging & Reporting Agents  

Each category serves a distinct role in the lifecycle of work.

---

## Governance Agents

**Location:** `AGENTS/GOVERNANCE/`

Governance agents define:
- Authority boundaries
- Approval gates
- Escalation paths
- Organizational rules

These agents **do not produce work**.  
They define **how work is allowed to proceed**.

---

## Planning & Architecture Agents

**Location:** `AGENTS/CHATGPT/`

These agents are responsible for:
- Translating approved intent into structured plans
- Producing architectural artifacts
- Enforcing design discipline
- Defining task boundaries

They **never execute code** and **never approve releases**.

---

## Human-Operations Agents

**Location:** `AGENTS/MOTION_AI/`

These agents interface with humans by:
- Capturing meeting context
- Drafting communications
- Managing schedules
- Normalizing raw human input

They **capture intent** but do not interpret or decide.

---

## Execution Agents

**Locations:**  
- `AGENTS/FRONTEND/`  
- `AGENTS/BACKEND/`

Execution agents:
- Implement approved tasks only
- Operate within a single, clearly defined scope
- Produce verifiable artifacts

They do not design systems or change scope.

---

## Quality & Verification Agents

**Location:** `AGENTS/JULES/`

These agents:
- Run tests
- Perform audits
- Validate security and performance
- Enforce quality gates

They never modify code directly.

---

## Logging & Reporting Agents

**Location:** `AGENTS/LOGGING/`

These agents:
- Capture execution logs
- Update institutional memory
- Produce executive summaries

They do not influence execution decisions.

---

## Authority Model

All agents operate under the following hierarchy:

1. **Mission Control (Human)** – Final authority
2. **Governance Rules** – Enforced mechanically
3. **Planning Agents** – Design and decomposition
4. **Execution Agents** – Implementation
5. **Verification Agents** – Independent checks
6. **Logging Agents** – Historical record

---

## Enforcement Rule

If an agent’s action is not explicitly allowed in its role definition, it is **forbidden by default**.

Violations must trigger escalation.

