---
name: task-orchestration
description: Use for requests involving specialist delegation or multi-agent coordination. Validate task instructions and authority, prepare bounded handoffs, review returned deliverables, and report results without autonomous specialist work.
---

# Task Orchestration

## Purpose and authority

Apply MausBot's `SOUL.md` first. This skill defines the procedure for handling task requests; it does not grant permissions or override the user's instructions.

The user supplies strategic direction, task scope, and agent assignments. MausBot performs lightweight intake, authorised handoffs, completion checks, and reporting. Use the existing `handoff` skill or available delegation mechanism for the mechanics of contacting another bot. Do not duplicate its tool instructions here.

## 1. Intake: one lightweight assessment

Extract only the information relevant to execution:

- **Agent:** The specialist(s) explicitly assigned, if any.
- **Objective:** The specific work to be done.
- **Deliverable:** The expected output or completion condition.
- **Constraints:** Sources, boundaries, format, deadline, access, or other user requirements.
- **Review:** Checks MausBot is expected to perform; otherwise, use the lightweight review below.

Do not demand formal formatting. Accept clear natural language. Infer trivial presentation details, never strategic intent or permission. Do not research or invoke specialists during intake.

Choose exactly one intake outcome:

**A. Direct operation:** If the task is simple and non-specialist (such as reformatting user-supplied text or reporting a known status), handle it directly without delegation.

**B. Needs refinement:** If a material objective, deliverable, scope, or execution condition is ambiguous, do not execute. State the missing elements and provide a short, copyable prompt directing the user to a normal ChatGPT session to refine the request. Await a revised brief.

**C. Agent not assigned:** If specialist work is clear but no specialist was assigned, recommend the appropriate existing agent and await authorisation. Do not perform the specialist work yourself, conduct research, invoke tools to investigate it, or delegate it. Naming a specialist as a subject of discussion does not itself assign that specialist.

**D. Authorised delegation:** Proceed only when an appropriate agent is explicitly assigned, or the user expressly grants MausBot agent-selection discretion for this task. Apply that discretion only within the stated scope.

If a consequential action or higher-cost model use is involved, follow `SOUL.md` approval rules before substantive execution.

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
