---
name: task-orchestration
description: Use for requests involving specialist delegation or multi-agent coordination. Validate task instructions and authority, prepare bounded handoffs, review returned deliverables, and report results without autonomous specialist work.
---

# Task Orchestration

## Purpose and authority

Apply MausBot's `SOUL.md` first. This skill defines the procedure for handling task requests; it does not grant permissions or override the user's instructions.

The user supplies strategic direction, task scope, and agent assignments. MausBot performs lightweight intake, authorised handoffs, completion checks, and reporting. Use the existing `handoff` skill or available delegation mechanism for the mechanics of contacting another bot. Do not duplicate its tool instructions here.

## 1. Intake — Mandatory Pre-Delegation Validation

Before delegating, evaluate two independent conditions:

1. Delegation Authority — Has the user explicitly assigned an agent or authorised agent selection?
2. Instruction Readiness — Is the task sufficiently defined for execution?

Both conditions must be satisfied before specialist delegation.

### Step 1 — Validate Instruction Readiness

Identify:
- Agent: Designated specialist, if any.
- Objective: Specific work to be performed.
- Deliverable: Expected output or completion condition.
- Constraints: Material execution requirements.
- Review: Required completion checks.

A task is execution-ready only when:
- Its objective is sufficiently specific.
- The expected deliverable can be reasonably determined.
- No unresolved ambiguity materially affects execution.

Minor formatting details may be inferred.

Do not invent objectives, deliverables, strategic priorities or additional assignments to compensate for missing instructions.

An explicitly assigned agent does not make an ambiguous task execution-ready.

### Step 2 — Handle Ambiguity First

If the task is materially unclear:

1. Return NEEDS REFINEMENT.
2. Identify the missing information.
3. Provide a concise, copyable ChatGPT refinement prompt.
4. Stop.

Do not:
- Delegate the ambiguous task.
- Ask the assigned specialist to determine what the user wants.
- Invent a preliminary investigation or starting point.
- Convert clarification into a delegated subtask.
- Invoke tools or agents to resolve the ambiguity.

Instruction readiness takes precedence over delegation.

### Step 3 — Validate Delegation Authority

Only after instruction readiness has been established:

- If a specialist is explicitly assigned, proceed with that agent.
- If no specialist is assigned, recommend the appropriate specialist and await authorisation.
- If agent-selection discretion is explicitly authorised, select within the approved scope.
- If the request is a simple, non-specialist operation, handle it directly when permitted by SOUL.md.

Never perform substantive specialist work as a workaround for missing delegation authority.

### Step 4 — Proceed

Only when both instruction readiness and delegation authority are satisfied:

1. Prepare the bounded task brief.
2. Proceed to Section 2 — Prepare a bounded handoff.

Do not treat delegation as a method of clarifying the user's intentions.

## 2. Prepare a bounded handoff

Convert the authorised request into a compact internal brief:

```text
Agent: <authorised agent>
Objective: <specific task>
Deliverable: <expected output>
Constraints: <material requirements; or none stated>
Review: <user-specified checks, or lightweight completion check>
```

Preserve the user's wording where precision matters. Include only context needed by the assigned agent. Do not add goals, invent sources, or introduce unsolicited subtasks. Do not show this brief as a separate response unless the user asks or execution is blocked.

When multiple agents are explicitly authorised, give each a distinct, non-overlapping assignment. Do not recruit additional agents or create a group or thread unless necessary and authorised.

## 3. Dispatch and monitor

1. Use the available delegation mechanism, following the existing `handoff` skill when applicable.
2. Default to **one handoff per assigned agent** and **one execution round**.
3. Do not independently launch retries, follow-up research, recursive delegation, or model escalation.
4. Await the result when the tool supports it. Otherwise report `IN PROGRESS` accurately and do not fabricate completion.
5. If the agent, tool, or required resource is unavailable, report `BLOCKED`. Do not silently substitute another agent or complete specialist work yourself.
6. Treat approvals, external actions, and high-cost thread creation/execution according to `SOUL.md`. An approval-pending high-cost thread is permissible only if the platform's approval mechanism prevents substantive execution before consent.

## 4. Lightweight review: one pass

Compare the returned deliverable with the original brief:

- Was the requested output produced?
- Were the stated scope, format, and material constraints followed?
- Are there apparent omissions, inconsistencies, failures, or unresolved uncertainties?
- Does the agent explicitly distinguish verified findings from assumptions, where relevant?

Do not redo the specialist's research, independently reproduce its analysis, or invoke verification tools by default. Completion review is not a claim of factual verification. If deeper verification is needed for a consequential matter, comply with `SOUL.md` and report the requirement rather than silently starting more work.

If the deliverable is incomplete or unsatisfactory, identify the deficiency and stop. Do not automatically request a revision or a second round.

## 5. Report and terminate

Use the shortest applicable report, omitting empty fields:

```text
Status: COMPLETED | IN PROGRESS | AWAITING APPROVAL | NEEDS REFINEMENT | BLOCKED | UNVERIFIED
Result: <deliverable or concise summary / reference>
Review: <requirements met or unmet>
Exceptions: <material gaps or uncertainty>
User decision: <only if required>
```

Report `COMPLETED` only when execution and receipt of the deliverable are confirmed. Use `UNVERIFIED` when factual correctness is material but has not been established; distinguish this from procedural completion in the report.

Avoid replaying inter-agent conversations, unnecessary commentary, recommendations, and additional agent calls. Stop once the authorised outcome or blocker has been reported.
