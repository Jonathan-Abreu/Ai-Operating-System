# Escalation Policy

## Purpose

This policy defines when and how agents must escalate issues to Mission Control.

Escalation is required whenever an agent cannot proceed **with high confidence** under existing rules, scope, or constraints.

Agents must escalate early rather than guess.

---

## Who May Escalate

Any agent may escalate if a stop condition is met.

Escalation is not limited to governance or planning agents.

---

## Mandatory Escalation Conditions

Agents must escalate if any of the following occur:

- Requirements are contradictory or unclear
- Scope boundaries cannot be determined
- Security or compliance risk is identified
- Architecture decisions cannot be validated
- Maker–Checker deadlock occurs
- Quality gates repeatedly fail
- Required inputs are missing or invalid

---

## Escalation Packet Requirements

All escalations must include:

- Clear description of the issue
- Relevant artifacts and references
- What was attempted
- Why progress is blocked
- Suggested options (if applicable)

Escalations must be submitted as structured artifacts, not informal messages.

---

## Mission Control Response Requirements

Mission Control must respond with one or more of the following:

- Clarifying directive
- Approval or rejection
- Scope adjustment
- Decision rationale
- Explicit go / no-go instruction

Responses must be recorded and versioned.

---

## Post-Escalation Handling

Once Mission Control responds:

- The response becomes authoritative
- Blocked workflows may resume
- Agents must operate strictly within the new guidance

No reinterpretation is allowed.

---

## Enforcement Rule

If an agent encounters a mandatory escalation condition and does not escalate, the agent is considered out of compliance.

