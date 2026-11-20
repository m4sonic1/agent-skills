---
name: task-and-schedule
description: Use when Assistant is assigned to organise tasks, track deadlines, prepare schedules, identify scheduling conflicts, or manage academic administration.
---

# Task and Schedule Management

## Purpose

Organise the user's commitments, deadlines and administrative workload accurately and efficiently.

This skill defines operational procedures. Assistant's SOUL.md governs authority, permissions and behavioural restrictions.

## 1. Task Intake

Identify the requested operation:

- Task organisation
- Deadline tracking
- Schedule preparation
- Scheduling conflict analysis
- Daily or weekly planning
- Academic administration

Extract relevant information:
- Tasks or commitments
- Dates and times
- Deadlines
- User-defined priorities
- Available time slots
- Scheduling constraints
- Required deliverable

Do not require information irrelevant to the requested operation.

If essential information is missing, report the specific ambiguity.

For delegated tasks, report missing requirements to MausBot.

Do not invent additional assignments.

## 2. Information Handling

Use information provided by the user or retrieved from authorised sources.

Distinguish:
- Confirmed commitments
- Proposed arrangements
- Hypothetical information
- Unverified information

Preserve original task names, dates, times and deadlines unless instructed otherwise.

Use the user's local timezone unless another timezone is specified.

Do not claim access to current calendar or task records unless those records were actually retrieved.

Do not fabricate unavailable information.

## 3. Task Organisation

When organising tasks:

1. Extract the relevant tasks and deadlines.
2. Identify explicitly supplied priorities.
3. Sort according to the user's requested criteria.
4. Identify apparent conflicts or missing information.
5. Return the requested list or structured summary.

Do not independently modify priorities.

Do not create additional tasks unless explicitly requested.

## 4. Schedule Preparation

When preparing a schedule:

1. Identify confirmed commitments.
2. Identify available scheduling windows.
3. Identify the work to be scheduled.
4. Respect user-specified deadlines and constraints.
5. Construct the proposed schedule.
6. Check for conflicts, omissions and impossible arrangements.

Do not silently move confirmed commitments.

Label proposed arrangements clearly.

If the available time is insufficient, report the conflict rather than inventing additional availability.

## 5. Academic Administration

For academic tasks:

- Organise assignment deadlines.
- Prepare study timetables.
- Consolidate known academic commitments.
- Identify approaching submission dates.
- Structure user-authorised revision plans.

Do not independently perform academic research or complete substantive academic assignments.

Refer specialist work back to the requesting party when necessary.

Do not independently delegate to other agents.

## 6. External Actions

Preparing a schedule does not authorise changing the user's actual calendar.

Before creating, modifying or cancelling external commitments, follow SOUL.md approval requirements.

Do not:
- Make unapproved calendar changes.
- Send external communications.
- Modify unrelated records.
- Establish new recurring routines without authorisation.

Never claim an external action was completed without confirmation from the relevant tool.

## 7. Output and Verification

Return the requested deliverable in the most suitable concise format.

Before reporting completion, verify:
- All requested items are included.
- Dates and times are preserved.
- User constraints are respected.
- Scheduling conflicts are identified.
- Proposed events are distinguished from confirmed events.

Report material limitations.

Avoid unnecessary reasoning, tool calls and commentary.

For MausBot delegations, return the completed deliverable and any material exceptions.

Stop after fulfilling the authorised assignment.
