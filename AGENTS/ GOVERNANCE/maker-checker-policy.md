# Maker–Checker Policy

## Purpose

This policy enforces the **Maker–Checker pattern** across the AI Operating System.

Any artifact produced by one agent (the Maker) must be independently reviewed by a different agent (the Checker) before it can be accepted, merged, or acted upon.

Self-certification is strictly forbidden.

---

## Definitions

- **Maker**: The agent that produces an artifact
- **Checker**: An independent agent responsible for reviewing that artifact
- **Artifact**: Any versioned output that influences planning, execution, or release

---

## Mandatory Application

The Maker–Checker pattern applies to, but is not limited to:

- PRDs
- Architecture documents
- ADRs
- Agent Task Maps
- Code changes
- Test results
- Release readiness memos

---

## Checker Independence Rules

A Checker must:
- Be a different agent than the Maker
- Have no execution responsibility for the artifact
- Operate with a review-only mandate

A Checker may:
- Approve the artifact
- Request amendments
- Reject the artifact

A Checker may not:
- Modify the artifact directly
- Override governance rules
- Approve their own work

---

## Review Outcomes

Each review must result in one of the following outcomes:

1. **Approved** — Artifact may proceed
2. **Amendments Required** — Artifact must be revised by the Maker
3. **Rejected** — Artifact is invalid and must be reworked

All outcomes must be recorded.

---

## Loopback Enforcement

If amendments are required:
- The artifact is returned to the original Maker
- The Maker must revise and resubmit
- The Checker must re-review the updated version

No bypassing is permitted.

---

## Escalation Conditions

Escalation to Mission Control is required if:
- Maker and Checker cannot reach agreement
- Requirements are contradictory
- Risk cannot be mitigated
- Repeated amendment cycles occur

---

## Enforcement Rule

No artifact may progress to execution or release without:
- A recorded Maker
- A recorded Checker
- A recorded review outcome

