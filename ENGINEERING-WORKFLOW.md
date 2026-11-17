# Engineering Workflow — Think, Plan, Code, Verify, Commit

## Purpose

Use this workflow when implementing a professional software task, not only when learning a new concept. The goal is to turn a requirement into a correct, reviewable change without keeping too many unresolved questions in working memory.

**Core principle: Think clearly before coding, implement in small verified slices, and make every open question visible.**

This is a guide, not bureaucracy. Scale the amount of planning to the risk and size of the task.

## The five phases

### 1. Think — understand the requirement

Before opening the editor or changing code, write down:

- What problem is the user or system experiencing?
- What behaviour must change?
- What is the expected input and output?
- What business rules must be preserved?
- What should happen for missing, invalid, duplicate, or unexpected data?
- What must not change?
- How will success be verified?

Inspect the relevant code paths and follow existing project conventions. Do not assume the requirement describes the implementation.

**Exit condition:** I can explain the expected behaviour and important boundaries in my own words.

### 2. Plan — create a small implementation map

Break the work into steps small enough to verify independently. For a typical Spring Boot API, this might be:

1. Inspect existing endpoint and project conventions.
2. Inspect relevant schema, relationships, and existing queries.
3. Define request/response contract and business rules.
4. Implement repository/data access.
5. Implement service/business logic.
6. Implement controller/API mapping.
7. Add validation and error handling.
8. Add unit and integration tests.
9. Verify the full request path.
10. Review the diff and commit.

Not every task needs every layer. Avoid adding layers or abstractions that the task does not need.

**Exit condition:** I know the next concrete step and what evidence will show it works.

### 3. Code — implement in small vertical slices

- Start with the smallest useful working path.
- Change one logical unit at a time.
- Compile or run focused tests frequently.
- Prefer a small end-to-end slice over implementing many disconnected layers.
- Follow the repository's conventions unless there is a reason to change them.
- Do not refactor unrelated code while implementing a focused task.
- Keep the diff reviewable.

A vertical slice should deliver a small piece of observable behaviour, for example: repository query + service call + focused test.

### 4. Verify — prove the behaviour

Check more than the happy path:

- Expected valid input.
- Missing or malformed input.
- Empty result.
- Boundary values.
- Duplicate or repeated requests where relevant.
- Authorization and data isolation where relevant.
- Database and downstream-service failures.
- Performance implications for large data sets when relevant.

Use the appropriate evidence: unit tests, integration tests, API requests, SQL results, logs, metrics, benchmarks, or reproducible manual checks.

Do not claim something is verified if it was only inspected or assumed.

### 5. Commit — leave a reviewable result

Before committing:

- Review the complete diff.
- Remove debug code, accidental files, secrets, and unrelated changes.
- Run relevant tests and record any tests that could not be run.
- Update documentation where behaviour or setup changed.
- Use a commit message that states the change clearly.

A commit should represent a coherent, understandable unit of work.

## The Open Loops system

Never keep unresolved questions only in working memory. Write them down and classify them.

### A. Blocking — investigate now

A question blocks progress if guessing could make the implementation incorrect, insecure, unreliable, or incompatible.

Examples:
- Should inactive records be returned?
- What is the expected behaviour for an unknown identifier?
- Which transaction boundary protects this update?
- Is this field nullable in production data?

Resolve blocking questions before relying on an assumption.

### B. Parked — research later

A question is parked if it is interesting but does not affect the correctness of the current change or the next implementation step.

Examples:
- How does Hibernate internally generate every SQL statement?
- How does Spring Boot discover all auto-configurations?
- How does PostgreSQL implement its buffer manager internally?

Record it in the Curiosity Parking Lot. Return to it when a real implementation issue makes it relevant or schedule separate study time.

### C. Resolved — record the decision

Write down the answer and the decision made. Include the reason and evidence when useful.

Example:
- Decision: return an empty list when no records match.
- Reason: this matches the established API contract.
- Evidence: existing endpoint convention and test.

## The interruption rule for deep dives

When research starts expanding during implementation, ask:

1. Does this question block the next coding step?
2. Could ignoring it cause a correctness, security, data integrity, or reliability issue?
3. Is there a smaller experiment that can answer it?
4. Can I park it and continue with the smallest safe implementation?

If it does not block the work, park it and return to the planned coding step.

Suggested coaching interruption:

> This is a useful technical rabbit hole, but does it block the current change? If not, capture it in the parked list. What is the smallest next implementation step, and how will we verify it?

Do not park questions whose answers are necessary for safe or correct behaviour.

## A lightweight task worksheet

Copy this into a task note or pull request description:

### Requirement
- Problem:
- Expected behaviour:
- Inputs and outputs:
- Business rules:
- Out of scope:

### Plan
- [ ] Inspect existing implementation and conventions.
- [ ] Identify data dependencies and contracts.
- [ ] Break work into small steps.
- [ ] Define tests and verification evidence.

### Open loops

| Question | Blocking? | Owner / next action | Status |
|---|---|---|---|
| | Yes / No | | Open |

### Decisions

| Decision | Reason / evidence |
|---|---|
| | |

### Implementation slices

| Slice | Expected behaviour | Verification | Status |
|---|---|---|---|
| | | | Not started |

### Verification
- Tests run:
- Manual checks:
- Edge cases:
- Known limitations:

### Commit
- Diff reviewed:
- Commit message:
- Commit SHA / PR:
- Remaining follow-ups:

## How to make the process faster

Speed comes from reducing rework and context switching, not from typing faster.

- Clarify high-impact ambiguity early.
- Inspect existing code before designing a parallel solution.
- Write down the next step instead of repeatedly reconsidering the whole task.
- Use focused tests to shorten feedback loops.
- Time-box investigation, but never time-box away necessary correctness or safety checks.
- Park non-blocking curiosity.
- Keep commits small and coherent.
- Automate repeatable checks where the project supports it.

## Definition of a completed task

A task is complete when:

- The requested behaviour is implemented.
- Important business rules and edge cases are addressed.
- Relevant tests or verification have been run.
- The diff has been reviewed.
- Known limitations and unverified checks are disclosed.
- The change is committed or ready for review.

**Think clearly. Plan the next slice. Code. Verify. Commit. Keep open loops visible.**
