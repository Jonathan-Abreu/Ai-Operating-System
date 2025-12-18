# Approval Gates

## Purpose

This document defines the **mandatory approval gates** within the AI Operating System.

An approval gate is a **hard stop** where automation must pause until Mission Control provides explicit approval or rejection.

No agent may proceed past a gate without a recorded decision.

---

## Gate 1 — Intent Approval

### Trigger
- Receipt of a new Intent Packet
- Receipt of new client context
- Significant change in client direction

### Required Artifacts
- Intent Packet
- Supporting context (if applicable)

### Decision Required
- Approve intent
- Reject intent
- Request clarification

---

## Gate 2 — Architecture & Scope Approval

### Trigger
- Completion of PRD
- Completion of Architecture document
- Completion of ADR drafts

### Required Artifacts
- PRD
- Architecture document
- ADR drafts
- Reviewer amendment summaries (if any)

### Decision Required
- Approve scope and architecture
- Request changes
- Reject proposal

---

## Gate 3 — Scope Change Approval

### Trigger
- Any proposed change after scope lock
- New requirements discovered during execution
- Architectural deviation request

### Required Artifacts
- Scope change proposal
- Impact analysis
- Updated ADR (if applicable)

### Decision Required
- Approve scope change
- Reject scope change

---

## Gate 4 — Release Approval

### Trigger
- Successful completion of all execution tasks
- Passing all quality and security checks

### Required Artifacts
- Release readiness memo
- Quality reports (Jules)
- Execution summaries

### Decision Required
- Go (approve release)
- No-Go (block release)

---

## Gate Enforcement

- All gates must be enforced mechanically via workflow automation
- Approval must be explicit and recorded
- Silence is not approval

---

## Violation Handling

If any agent attempts to bypass an approval gate:
- Execution must halt immediately
- An escalation packet must be generated
- Mission Control must be notified

