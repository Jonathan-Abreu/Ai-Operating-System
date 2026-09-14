# AIOS-001 — Claude → Copilot Handoff

> **Temporary continuity bridge. NOT a constitutional source of truth.**
> This file exists so GitHub Copilot can continue AIOS-001 using GitHub alone — without Notion, Slack, Grok, or any prior AI conversation. Once the governance bootstrap lands and canonical locations exist, this file is superseded and should be retired with a supersession record.

**Handoff from:** Claude Code · **Handoff to:** GitHub Copilot · **Date:** 2026-09-14

---

## 1. Project

| Field | Value |
|---|---|
| **Project ID** | `AIOS-001` |
| **Project** | AI Operating System |
| **Mission** | Build a functional MVP AI Operating System for governed AI-assisted software development. |
| **Execution mode** | `SINGLE_ACTIVE_PROJECT` |
| **Active project** | `AIOS-001` (itself — the OS is its own first project) |
| **Target milestone** | AI-OS v1.0 — Functional Development Kernel |

The AI-OS coordinates interchangeable AI runtimes through persistent organizational roles, structured contracts, governed GitHub execution, independent validation, and durable handoffs. Mission Control (`Jonathan-Abreu`) is the sole human final authority.

---

## 2. Repository state

| Field | Value |
|---|---|
| Repository | `Jonathan-Abreu/Ai-Operating-System` (private, **user-owned**, not an org) |
| Default / only branch before this handoff | `main` |
| **Baseline HEAD** | `40b8201013816f2a7c10dfb15bb1ecebae8e6ae1` (2025-12-19T00:37:52Z) |
| Branch protection on `main` | **none** — `protected: false` |
| Rulesets configured | **none** (`GET /rulesets` → `200 []`) |
| Total commits | **118** (all committer `web-flow`, i.e. made via GitHub web UI) |
| Pull requests ever | **0** before this handoff PR |
| Working tree | Clean. This handoff branch adds only the two files named in §14. |

### Current structure at baseline HEAD

```
/
├── README.md                  (~4.5 KB, substantive; still couples governance to n8n)
├── AGENTS/
│   ├── 00_AGENT_OVERVIEW.md
│   ├── " FRONTEND"/           ⚠ LEADING SPACE in directory name (5 charters)
│   ├── " GOVERNANCE"/         ⚠ LEADING SPACE (4 files)
│   ├── " RESEARCH"/           ⚠ LEADING SPACE (3 charters)
│   ├── BACKEND/               (6 charters)
│   ├── CHATGPT/               (7 charters — provider-named, must be decoupled)
│   ├── JULES/                 (5 charters — provider-named)
│   ├── LOGGING/               (2 charters)
│   └── MOTION_AI/             (4 charters — provider-named)
├── PACKETS/                   (7 files — ALL 1-byte empty stubs)
├── STANDARDS/                 (7 files — ALL 1-byte empty stubs)
├── TEMPLATES/                 (5 files — ALL 1-byte empty stubs)
└── WORKFLOWS/                 (7 files — ALL 1-byte empty stubs)
```

**Role charter count:** 33 role definitions + 3 governance policy documents + 1 overview = 37 `.md` files under `AGENTS/`. (33 includes `mission-control.md`. Do not double-count it as both a role and a fourth governance policy — that error has occurred before.)

### The 26 empty stubs

All 26 share blob SHA `8b137891791fe96927ad78e64b0aad7bded08bdc` (a single newline):

- `PACKETS/` (7): blocker, email-draft, intent, meeting-context, release-readiness-memo, schedule-change, work-log
- `WORKFLOWS/` (7): execution-routing, jules-quality-gate, knowledge-capture, motion-context-ingestion, n8n-architecture, planning-orchestration, telegram-intake
- `STANDARDS/` (7): artifact-ownership, file-naming-conventions, logging-requirements, observability-alerting-baseline, release-policy, security-baseline, stack-selection-policy
- `TEMPLATES/` (5): adr, agent-task-spec, executive-brief, incident-postmortem, pr

### What does NOT yet exist

`.github/` · `CODEOWNERS` · PR template · any CI/Actions · any ruleset or branch protection · `CONTRACTS/` · `RUNTIMES/` · `ROLES/` · `ADRs/` · `CONSTITUTION/` · `CHANGELOG` · `VERSION` · any packet or handoff schema · any registry (role/capability/permission/runtime/project) · any CLI or tooling · any test suite · any Control Plane.

### Known legacy problems

1. **Three leading-space directories** (` FRONTEND`, ` GOVERNANCE`, ` RESEARCH`) — real Git paths. Any automation must quote them exactly until remediated.
2. **Provider-named role directories** (`CHATGPT/`, `JULES/`, `MOTION_AI/`) — contradict approved ADR-0001. Must be decoupled, **not** deleted.
3. **26 empty stubs** — filenames promise contracts that do not exist.
4. **`AGENTS/LOGGING/executive-summary-agent.md` is truncated** — ends mid-sentence at `- Mask`.
5. **`00_AGENT_OVERVIEW.md` omits RESEARCH** and cites paths without their leading spaces — documentation contradicts filesystem.
6. **README still states governance is "orchestrated mechanically via n8n"** while `WORKFLOWS/n8n-architecture.md` is an empty stub. n8n is **not** OS law.
7. **Zero PRs, 118 direct-to-main commits** — the repo has never exercised maker–checker.

---

## 3. Current phase

**All governance-bootstrap decision blockers are CLOSED. The repository is at `GOVERNANCE_BOOTSTRAP_READY`.**

Archaeology, requirements-gap analysis, technology research, target architecture, ADR drafting, Mission Control disposition of the bootstrap-blocking forks, and independent validation have all occurred. **No governance has been implemented yet.** The repository is still exactly as it was on 2025-12-19 apart from this handoff branch.

The next step is the **bounded governance bootstrap** — see §8.

---

## 4. BINDING Mission Control decisions

Everything in this section is **APPROVED and binding**. Implement to it. Do not reopen it without contradictory durable evidence.

### 4.1 ADR-0001 — Model-independent roles (APPROVED WITH CONDITIONS)

**The operating chain is:**

```
ROLE → CAPABILITY → PERMISSION → CONTRACT → RUNTIME
```

- **Roles are persistent organizational identities.** Role titles and paths must **never** contain a vendor or product brand (ChatGPT, Jules, Motion, Gemini, Grok, Claude, Codex, Cursor, n8n, Telegram).
- **Providers are runtimes only.** A runtime binds to a role as *data in a registry*; changing the stack is a registry change, never a charter rewrite.
- **Capabilities** are declared independently of roles and runtimes: `PLAN`, `REVIEW`, `IMPLEMENT`, `VERIFY`, `RESEARCH`, `HUMAN_OPS`, `LOG`, `GOVERN`.
- **Permissions** live in an org-wide matrix; charters may narrow, never widen.
- **Mission Control is human-only (`GOVERN`)** and is not a swappable runtime role.
- **Migration is evolutionary.** Provider-named directories are deprecated *as identity* with an alias period — **not silently deleted**. Leading-space directories are remediated via recorded `git mv`.
- Approved role taxonomy: `ROLES/` parent with domain subdirectories (Option B). RESEARCH is an independent seventh domain.

### 4.2 MC-30 — Identity model (ART-93)

| Function | Identity |
|---|---|
| Mission Control / independent human checker | **`Jonathan-Abreu`** |
| AI implementation / maker identity | **`aios-runtime`** *(provisional name; does not exist yet)* |
| Required approval / CODEOWNER authority | **`Jonathan-Abreu`** |
| Merge authority | **Mission Control**, unless later governance explicitly delegates low-risk merges |

**`aios-runtime` MAY:** create branches, commit, push, open/update PRs, respond to review findings, perform other authorized implementation actions.

**`aios-runtime` MUST NOT:** satisfy the independent approval requirement for its own work · approve its own governed PRs · bypass required review · act as Mission Control · be placed in CODEOWNERS to satisfy its own review gate.

**Provider ≠ identity.** Claude Code, Copilot, Jules, ChatGPT/Codex and future runtimes all operate through the **same** maker identity where technically appropriate. One identity, many runtimes.

### 4.3 MC-02 — G1 GitHub-first governance (ART-94)

**GitHub-first enforcement is the approved governance model.** The enforcement plane uses GitHub-native controls:

1. Pull-request-required change flow
2. Protected / default-branch governance
3. Required independent review
4. CODEOWNERS or equivalent ownership controls
5. Required status checks
6. Automated schema / governance validation
7. Explicit bypass policy
8. Auditable merge controls

**External orchestration engines are NOT the primary governance authority and are NOT required OS law.** A hybrid model may be added only through separately approved scope.

**Substrate:** GitHub **Rulesets** are preferred, based on live capability evidence (`GET /rulesets` → `200 []` on 2026-09-14; an earlier `403 "Upgrade to GitHub Pro"` plan gate is gone). **Create capability must still be confirmed in the GitHub web UI before activation.** If Rulesets cannot be created or cannot enforce the required controls, use the strongest supported GitHub-native mechanism satisfying the same contract — **without reopening G1**.

> Any document in Notion or elsewhere claiming this repository is limited to *classic branch protection only* is **superseded**. That claim came from a documentation reading, not a live test.

### 4.4 MC-06 — Staged enforcement + break-glass (ART-95)

**Bypass model:**

- `aios-runtime` — **NO bypass authority.** May never bypass its own governance.
- `Jonathan-Abreu` — **sole break-glass actor**, **PR-scoped** where Rulesets support it, not unrestricted direct-push bypass.
- **No blanket grant** to repository admins as a class, write-role users, Copilot, Claude, Jules, or generic automation.

**Binding constraints:** bypass ≠ approval · bypass does **not** satisfy maker–checker · break-glass is emergency/recovery only, never a normal merge path · Mission Control remains accountable for emergency use · every break-glass event must be durably logged with **reason, affected PR/commit, controls bypassed, and follow-up remediation**.

**Staged rollout (binding preference order):**

1. If the UI exposes **Evaluate**, configure and observe in Evaluate first.
2. If Evaluate is unavailable but Rulesets can be created, stage `Disabled` → configuration review → `Active`.
3. **Before Active, all five must pass:** MC recovery/bypass path works · required checks actually report · required review can be satisfied · `aios-runtime` cannot bypass · normal PR flow remains usable.
4. **Do not activate** until bootstrap configuration and recovery path have been **independently checked**.

> **Capability coupling to be aware of:** PR-scoped bypass is a *Rulesets* feature. Classic branch protection's admin bypass is effectively binary. If Rulesets prove unavailable, the PR-scoped element may not be implementable as written — **return to Mission Control rather than silently degrading to unrestricted bypass.**

### 4.5 MC-04 — Signed commits DEFERRED (ART-96)

**Signed commits are NOT required by the governance bootstrap. Do not make signing a bootstrap blocker.**

Basis: commit-signing capability is unverified across Claude Code, Copilot, Jules and Codex. A signing rule must not become an accidental runtime lockout on the shared maker identity.

MVP integrity relies instead on: governed branch + PR flow · no direct mutation of protected `main` · required status checks · required independent review · maker cannot approve or bypass own work · MC holds approval and merge authority · full auditability.

Post-MVP, signing may be enabled after a runtime compatibility study (Claude Code, Copilot, Jules, Codex; API-created vs git-push commits; key storage and rotation). Enabling it later does **not** change G1.

### 4.6 Block 0.1 (ART-25) and Block 0.2 (ART-26)

- **Block 0.1:** grant an agent runtime commit rights as a distinct GitHub identity. *(Principle; MC-30 supplies the implementation.)*
- **Block 0.2:** **build governance BEFORE substantive remediation** — but **activation must follow implementation AND verification of the distinct checker identity.** Goal: remediation PRs themselves run through the new governance rather than leaving `main` nominally frozen during remediation.

### 4.7 ADR-0002 locks needed for implementation continuity

The Amended ADR-0002 is **still Under Review / MC Pending** (see §5), but these component forks were separately **Approved** and are binding:

- **Block 3.2 — Nine constitutional packet types:** `intent`, `meeting-context`, `email-draft`, `schedule-change`, `work-log`, `blocker`, `release-readiness`, `handoff`, `work-packet`. All seven legacy packet names are preserved; `handoff` and `work-packet` are new.
- **Block 3.3 (ART-49) — PRESERVE / DEFER stubs.** Empty ≠ archive. Preserve stub presence; **defer fill until authorized remediation.** Archive only with durable migration evidence.
- **Block 3.5a (ART-57) — ADR-0002 is PACKET-SCOPED.** It owns the packet/handoff contract domain only. `WORKFLOWS/`, `STANDARDS/`, `TEMPLATES/` stay **outside** ADR-0002 under the Target Architecture §10.4 umbrella.
- **Block 3.5b (ART-62) — A1 CANONICAL MIGRATION (topology only).** Canonical path for packet/handoff contracts is **`CONTRACTS/PACKETS/`**. Legacy `PACKETS/*` become *temporary noncanonical compatibility pointers only*. Eight locks travel with this: single-source · pointer not duplicate · no false implementation claim · legacy seven only · evidence-gated retirement · no dual-write · scope frozen · **authorizes topology for planning only, no GitHub mutation**.
- **Block 3.4 (ART-54) — RISK-TIERED acknowledgement.** Default soft-required (required to close; missing ack = open continuity defect). Hard-gated only for high-risk/irreversible/security-sensitive/production-affecting/MC-gated transfers.
- **Block 3.1 (ART-45) — frozen common envelope + handoff body.** Envelope: `schema_version`, `packet_id`, `packet_type`, `created_at`, `created_by_role` (a `role_id`, never a provider), `project_id`, `correlation_id`, `status`, conditional `approver`, typed `links`. Handoff body adds: `goal`, `before_state`, `after_state`, `work_completed`, `decisions`, `files`, `commits`, `prs`, `requirements`, `verification`, `blockers`, `risks`, `unresolved_questions`, `prohibited_changes`, `next_action`, `next_role`, `confidence`, `acknowledgement`. Dual-form: human Markdown + machine JSON Schema. Evidence shape over vendor flags — fields like `jules_passed` are forbidden.

---

## 5. APPROVED vs PROPOSED — do not confuse these

| Artifact | Status | Treat as |
|---|---|---|
| **ADR-0001** (Amended, model-independent roles) | **APPROVED WITH CONDITIONS** | **LAW** |
| **PDR-2026-09-14-001** (provider decoupling / GAP-E-001) | **APPROVED** | **LAW** |
| **Blocks 0.1, 0.2, 1.1–1.5, 2.1–2.4, 3.1–3.5b** | **APPROVED** | **LAW** |
| **MC-30 / MC-02 / MC-06 / MC-04** (ART-93/94/95/96) | **APPROVED** | **LAW** |
| **Amended ADR-0002** (packet/handoff schemas) | **Under Review / MC Pending** | **NOT law.** Its component blocks above *are*. |
| **ADR-0003** (Knowledge SoT split) | **Proposed / Pending** | NOT law |
| **ADR-0004** (Runtime binding registry) | **Proposed / Pending** | NOT law |
| **ADR-0005** (Governance enforcement) | **Partially disposed** — Q1/Q3/Q5 closed (MC-02/04/06); Q2 resolved by constraint; **Q4 open** | Only the closed questions are law |
| **ADR-0006** (Control Plane deferral) | **Proposed / Pending** | NOT law |
| **ADR-0007** (Artifact distribution surfaces) | **Proposed / Pending** | NOT law |
| **ADR-0008** (Canonical landing) | **Proposed / Pending** | NOT law |
| **Target Architecture** | **PROPOSED** | NOT law. Must be disposed **last**; accepting it must not approve ADR-0002–0008 by reference. |

**Hard sequencing rule that survives into implementation:** **ADR-0003 must be disposed before ADR-0007.**

---

## 6. Open items

### BOOTSTRAP BLOCKERS — **NONE REMAINING**

All governance-bootstrap decision blockers are closed (MC-30, MC-02, MC-06, MC-04; MC-03 resolved by constraint).

### Capability checks still required before activation

| # | Check | Who | Status |
|---|---|---|---|
| C1 | Is **"New ruleset"** available? (Settings → Rules → Rulesets) | Mission Control | **UNVERIFIED** |
| C2 | Does **Enforcement status** offer **Evaluate**? | Mission Control | **UNVERIFIED** |
| C3 | Can any runtime actually authenticate as `aios-runtime`? | Mission Control | **UNRESOLVED — blocks the bootstrap PR** |

**C3 is a hard blocker.** The identity does not exist yet, and no runtime currently has credentials for it. Until it is provisioned *and* a runtime can assume it, the maker for the bootstrap PR is undetermined.

### MVP BLOCKERS (before AI-OS v1, not before bootstrap)

Amended ADR-0002 final disposition · ADR-0004 Q1 (registry pattern) · ADR-0004 Q3 (registry editors) · ADR-0003 Q1 (K2 target + K1 interim) · ADR-0008 F1 (ADR path casing) · ADR-0008 F2 (land vs approve sequencing) · ADR-0008 F4 (canonical field population).

### NONBLOCKING / POST-MVP

ADR-0005 Q4 (confirm n8n not OS law) · ADR-0004 Q2/Q4 · ADR-0003 Q2/Q3/Q4 (PM vendor remains deliberately open) · ADR-0006 Q1–Q4 · ADR-0008 F3/F5/F6 · ADR-0007 Q1–Q3 · Target Architecture acceptance · signed-commit hardening.

---

## 7. ⚠️ GitHub administration limitation — READ THIS

**The Claude Code GitHub App integration does NOT have repository `administration` permission.** Verified: `GET /branches/main/protection` → `403 Resource not accessible by integration`.

**Consequences:**

- No AI runtime operating through that integration can create or modify **rulesets, branch protection, or repository settings**.
- **Mission Control must apply all repository settings manually in the GitHub web UI.**
- **Copilot must NOT assume a setting exists merely because a policy document describes it.** Verify against the live API (`GET /rulesets`, `GET /rules/branches/main`, `list_branches`) before relying on any enforcement.

File writes are a separate permission and are available.

---

## 8. NEXT EXACT ACTION FOR COPILOT

**One bounded task. Nothing beyond it.**

> **Build the Governance Bootstrap implementation slice from the binding decisions in §4, then implement the bounded governance bootstrap in §9 — but only after Mission Control explicitly authorizes execution AND capability checks C1–C3 in §6 are resolved.**

**Authorization state as of this handoff:**

- ✅ Mission Control authorized a **continuity-only** GitHub write — that is this handoff branch and these two files. **Already performed.**
- ❌ Mission Control has **NOT** authorized governance bootstrap execution. A Governance Bootstrap Authorization Packet was prepared and delivered to Mission Control in the Claude session but is **still awaiting explicit authorization**.

**Therefore: do not begin §9 until Mission Control says so in a durable record.**

Do not "continue building AI-OS." Do not start MVP capabilities. Do not remediate stubs.

---

## 9. Governance bootstrap target scope (for when authorized)

### Files to create (bootstrap PR)

1. **`.github/CODEOWNERS`**
   ```
   # AI-OS — constitutional ownership
   # Mission Control is the required approving reviewer for MVP.
   # The AI maker identity (aios-runtime) is deliberately NOT listed here.
   # Per MC-30: a maker identity must never occupy CODEOWNERS to satisfy its own review gate.

   * @Jonathan-Abreu
   ```

2. **`.github/pull_request_template.md`** — Work Packet ID · objective · changes · maker/checker attestation ("I am not approving my own work") · validation checkboxes · prohibited-scope confirmation (no settings changed, no secrets, no unauthorized stub fills).

3. **`.github/workflows/os-path-hygiene.yml`** — fails a PR when a file **added or modified by that PR** has a leading/trailing space in a path segment, or introduces a provider-named role directory.
   > **Critical:** scope this to **changed files only**. The repository *currently contains* three leading-space directories. A repo-wide check would fail every PR, and fixing those paths is remediation — which is gated behind the activation that the failing check would block. That is circular. Changed-files scoping breaks the cycle and grandfathers legacy paths until remediation.

4. **`.github/workflows/os-schema-validate.yml`** — validates that any `.json`/`.yml`/`.yaml` **added or modified by the PR** parses. Passes trivially when none are touched. **State the limitation in-file: this does not validate against AI-OS contract schemas, because none exist yet.**

### Deliberately EXCLUDED from bootstrap

| Item | Why |
|---|---|
| `TEMPLATES/adr-template.md` fill | It is one of the 26 stubs. **ART-49 says PRESERVE/DEFER**, and Block 0.2 gates remediation. Some proposed documents put this in the first write — that conflicts with ART-49. **Awaiting a Mission Control ruling; do not fill it unilaterally.** |
| `ADRs/` directory | Path casing is ADR-0008 F1, **still open**. Creating it pre-empts an undisposed fork. |
| `os-adr-structure` workflow | Cannot know which path to validate until F1 closes. A no-op check that validates nothing creates false confidence — omit it rather than fake it. |
| Any stub fill, move, rename, archive | Remediation. Gated by Block 0.2. |
| Any repository settings change | Cannot be done by an AI integration (§7). Mission Control applies these. |

### Ruleset configuration (applied manually by Mission Control)

- **Target:** `main`
- **Enforcement:** `Evaluate` if available, else `Disabled` first
- **Bypass:** `Jonathan-Abreu` only, mode **"For pull requests only"**. No other actor.
- **Rules:** require PR before merging (required approvals **1**; require Code Owner review; dismiss stale approvals on push; require approval of most recent reviewable push) · block force pushes · restrict deletions · required status checks **added only after they demonstrably report** · **require signed commits: NO**

### Execution sequence

| Phase | Actor | Action |
|---|---|---|
| B0 | Mission Control | Create `aios-runtime`, add as **Write** collaborator, provision credential, resolve C3 |
| B1 | Mission Control | Perform C1 + C2; record live result |
| B2 | `aios-runtime` (maker) | Branch + commit the four files + open PR |
| B3 | Mission Control | Confirm both workflows actually run and report |
| B4 | Mission Control | Review, approve, merge |
| B5 | Mission Control | Create ruleset in staged mode |
| B6 | Mission Control | Run the five-point pre-Active checklist (§4.4) |
| B7 | Mission Control | Set enforcement **Active** |
| B8 | Independent checker | Independent validation — **the maker cannot self-certify** |

### Validation, rollback

**Validation:** confirm the four files exist · inspect ruleset enforcement/rules/bypass · confirm rules apply to `main` · confirm PR maker ≠ approver · confirm HEAD advanced by exactly one merge · **negative test: maker attempts self-approval → must fail** · **negative test: maker attempts direct push to `main` → must fail once Active**. The two negative tests are the only ones that prove *enforcement* rather than configuration.

**Rollback:** bad file content → revert via new commit or close PR unmerged · misconfigured ruleset → set `Disabled` or delete (MC, web UI) · lockout → MC PR-scoped break-glass, set `Disabled`, fix, re-stage, **log the event** · compromised identity → revoke collaborator access and token. **Under no failure mode is history rewritten, force-pushed, or deleted.**

**Prohibited until bootstrap validation completes:** any wider MVP implementation.

---

## 10. MVP target (direction, NOT the next task)

After governance is validated, AI-OS v1.0 eventually requires: provider-independent roles · capability registry · permission model · runtime registry · runtime binding · project registry with `MAX_ACTIVE_MUTATION_PROJECTS = 1` · project bootstrap · Work Packet contract · Handoff contract · remaining constitutional packet contracts · validation tooling · minimal operator CLI (`status`, `validate`, project lifecycle, work-packet, handoff, doctor) · core development workflows and state transitions · runtime adapters/instructions for ChatGPT, Claude, Claude Code, Copilot and Jules · mechanically enforced maker–checker · clean-room recovery.

**Deferred as non-goals for MVP:** dashboards, web apps, Control Plane database, multi-agent schedulers, autonomous deployment, simultaneous multi-project mutation, deep n8n automation, Kubernetes, replacing GitHub/Notion/Slack.

**The strongest MVP test:** a brand-new project can be created, and the OS can establish project → requirements → architecture → plan → Work Packet → role → runtime → implementation → independent review → handoff → next action, **with a runtime replaced mid-process and nothing lost.**

---

## 11. Source / provenance map

These IDs refer to Notion and Slack records **Copilot cannot access**. They are provenance only — **the binding substance is already written above.**

| ID | What |
|---|---|
| ART-93 | MC-30 — identity model disposition |
| ART-94 | MC-02 — G1 + substrate condition disposition |
| ART-95 | MC-06 — staged rollout + break-glass disposition |
| ART-96 | MC-04 — signed commits deferred disposition |
| ART-25 | Block 0.1 — second GitHub identity (principle) |
| ART-26 | Block 0.2 — ruleset timing / activation gate |
| ART-45 / ART-49 / ART-54 / ART-57 / ART-62 | ADR-0002 Blocks 3.1 / 3.3 / 3.4 / 3.5a / 3.5b |
| ART-71 | Amended ADR-0002 (Under Review / Pending) |
| ART-83 | Chronos HEAD verification at `40b8201` |
| ART-84 / ART-85 | RUN TO GITHUB-READY hub + Relay handoff |
| ART-87 | Axiom source-faithful fork wordings |
| ART-92 | Sentinel Part H validation (PASS WITH EXCEPTIONS) |
| ART-8 | Target Architecture (PROPOSED) |
| ART-7 | PDR-2026-09-14-001 provider decoupling (APPROVED) |

Slack channels (inaccessible to Copilot): `#documentation` `C0C1CMJAV5H` · `#ai-operating-system` `C0C1NBYPQA0` · `#ai-os-adrs` `C0C1JU24A82` · `#ai-os-design-review` `C0C1MPZAJHX`.

---

## 12. PROHIBITED ACTIONS FOR COPILOT

Copilot must **NOT**:

1. Reopen disposed Mission Control decisions without contradictory durable evidence
2. Treat Proposed ADRs as Approved (see §5)
3. Mutate `main` directly
4. Bypass maker–checker
5. Grant `aios-runtime` bypass authority
6. Require signed commits for MVP
7. Perform a broad repository rewrite
8. Delete or silently move legacy content — preserve, alias, and record supersession
9. Start multiple active mutation projects
10. Rely on Slack, Notion, Grok, or prior AI conversation context
11. **Invent missing decisions** — if a decision is absent, stop and escalate to Mission Control
12. Self-certify substantial implementation — use **IMPLEMENTATION COMPLETE — PENDING INDEPENDENT VALIDATION**
13. Assume a repository setting exists because a document describes it — verify against the live API

---

## 13. Continuity standard

Every meaningful session must leave a durable handoff recording: objective · work completed · state before/after · files changed · commits · tests and results · decisions · blockers · risks · unresolved questions · prohibited changes · next action · next role.

**No critical project state may exist only inside an AI conversation.**

---

## 14. This handoff

| Field | Value |
|---|---|
| Branch | `handoff/claude-to-copilot-aios-001` |
| Baseline | `40b8201013816f2a7c10dfb15bb1ecebae8e6ae1` |
| Files added | `AIOS-001-COPILOT-HANDOFF.md`, `AIOS-001-COPILOT-HANDOFF.yaml` |
| Scope | **Continuity documentation only.** No governance activation, restructuring, role migration, schema implementation, or remediation. |
| Merge state | **Do not merge without Mission Control.** |

---

*Prepared by Claude Code as maker. Not independently validated. Governance bootstrap execution NOT yet authorized.*
