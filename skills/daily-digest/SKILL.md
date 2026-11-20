---
name: daily-digest
description: Use when Assistant is explicitly assigned to prepare a daily or weekly administrative briefing from authorised scheduling, task and deadline information.
---

# Daily Digest

## Purpose

Produce concise, accurate administrative briefings from authorised information.

This skill governs how Assistant prepares a digest. It does not authorise scheduling routines, accessing new services, contacting other agents or modifying records.

SOUL.md governs authority and permissions.
MEMORY.md governs durable context and information provenance.

## 1. Activation

Execute only when:
- The user explicitly requests a digest.
- MausBot delegates a defined digest task.
- An existing, user-authorised routine invokes this skill.

Do not independently establish, enable, modify or expand recurring digest schedules.

Do not perform continuous monitoring or unsolicited follow-up checks.

## 2. Scope

A digest may include:
- Today's confirmed commitments.
- Upcoming appointments and deadlines.
- Outstanding administrative tasks.
- User-defined priorities.
- Scheduling conflicts.
- Items requiring the user's decision.
- Material changes since a previously verified briefing.

Daily and weekly digests follow the same process, with different reporting periods.

Do not undertake specialist research, financial analysis, software development or independent email triage.

## 3. Information Collection

Use only the sources authorised for the assignment:
- User-supplied information.
- Authorised calendar records.
- Authorised task-management records.
- Relevant verified administrative memory.
- Explicitly supplied outputs from other agents.

Retrieve only what is needed for the requested reporting period.

Do not independently request work from other agents.

Do not search unrelated files, messages or websites to make the digest more comprehensive.

If a source is inaccessible, report that limitation.

## 4. Information Validation

Before including an item:

1. Identify its source.
2. Establish whether it is confirmed, proposed, historical or unverified.
3. Check the relevant date and time.
4. Determine whether it falls within the reporting period.
5. Check for duplicates and conflicting information.

Never treat hypothetical exercises, validation tests or illustrative examples as genuine commitments.

Never convert an unverified historical deadline into a confirmed current obligation.

When sources conflict, identify the discrepancy rather than silently choosing one.

A previously saved digest is not proof that its underlying commitments remain current.

## 5. Reporting Period

Use the user's specified reporting period.

If no period is specified:
- Daily digest: the current calendar day.
- Weekly digest: the next seven calendar days, including today.

Use Asia/Singapore unless the user has explicitly established another relevant timezone.

Identify the date and reporting period in the output.

Do not silently expand the reporting period.

## 6. Prioritisation

Follow priorities explicitly established by the user.

Highlight:
- Approaching confirmed deadlines.
- Conflicting appointments.
- Overdue administrative tasks.
- Decisions requiring user input.

Urgency may be reported based on verified timing.

Do not assign strategic importance or reorder the user's priorities independently.

Do not create new tasks from observations unless explicitly instructed.

## 7. Digest Format

Use the following structure where relevant:

### Administrative Digest
As of: [Date and timezone]
Period: [Reporting period]

**Upcoming commitments**
- [Date/time — Confirmed commitment]

**Deadlines and outstanding tasks**
- [Deadline — Task — Confirmed status]

**Conflicts or exceptions**
- [Verified issue]

**Decisions required**
- [Specific unresolved decision]

**Information limitations**
- [Missing, inaccessible or unverified source]

Omit empty sections.

Keep routine digests concise, normally within 150–250 words unless additional detail is requested.

Do not include speculative productivity advice or motivational commentary.

If no records were accessible, say that information was unavailable. Do not claim there are no commitments.

## 8. Specialist Boundaries

Assistant owns administrative consolidation.

Inbox owns email triage.

Scout owns research.

Stooge and Scrooge own their respective financial responsibilities.

Do not independently access, analyse or summarise specialist-owned information unless it has been explicitly supplied for administrative consolidation.

A request for a combined cross-agent digest does not independently authorise contacting other agents.

Return missing specialist inputs or coordination requirements to MausBot or the user.

## 9. External Actions

Digest preparation is read-only.

Do not:
- Create or modify calendar events.
- Change task statuses.
- Send emails or messages.
- Create reminders or recurring routines.
- Modify agent settings or permissions.
- Write new personal memories from hypothetical or unverified information.

Actions beyond digest preparation require a separate, explicitly authorised assignment and applicable permission checks.

## 10. Verification and Completion

Before reporting completion, verify:

1. The reporting period is correct.
2. Included items have identifiable sources.
3. Dates, times and deadlines are accurate.
4. Hypothetical information is excluded.
5. No inaccessible source is presented as checked.
6. No unauthorised external action occurred.

Return the digest and any material limitations.

For MausBot delegations, return the deliverable and exceptions only.

Stop after completing the authorised task.
