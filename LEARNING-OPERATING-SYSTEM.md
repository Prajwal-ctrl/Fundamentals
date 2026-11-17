# Learning Operating System

## The goal

Learn deeply, but do not let research become a substitute for building.

**Core principle: Learn less at a time. Build while learning. Ship small, useful evidence of capability.**

Deep curiosity is an advantage. Unbounded deep dives are not. The objective is to preserve curiosity while making implementation happen early and consistently.

## The learning loop

1. **Understand the problem** — What problem does this concept solve? Why does it exist?
2. **Build a first mental model** — Explain the basic principle and mechanism in plain language.
3. **Start implementing early** — Build the smallest useful example before trying to understand every internal detail.
4. **Investigate through implementation** — Deep-dive into internals when a real implementation question, bug, limitation, or design decision gives the investigation a purpose.
5. **Test and break it** — Try edge cases, failure scenarios, and alternatives.
6. **Explain and ship** — Explain the result in your own words, document it, and commit the working artifact.

## The anti-rabbit-hole rules

- Do not wait for complete understanding before writing code.
- After roughly two focused learning sessions on a topic, begin a minimal implementation. Treat this as a guardrail, not a rigid law.
- If a question is interesting but does not block the current implementation, put it in the **Curiosity Parking Lot**.
- Investigate a parked question immediately only if it affects correctness, security, reliability, or the next implementation step.
- Prefer a small working result today over a perfect theoretical understanding that never becomes a working result.
- Do not confuse finishing a course or reading documentation with completing a skill.

## The 70% start-building rule

Start implementation once you can:

- State the problem the concept solves.
- Explain its basic principle.
- Describe its basic execution flow.
- Identify one realistic use case.

You do not need to know every internal detail. Let implementation reveal which details matter next.

## The interruption protocol

When I notice that I am repeatedly expanding the theory, researching increasingly low-level details, or postponing the first working version, I want my learning coach (ChatGPT) to interrupt me constructively:

1. Point out that I am going deeper before producing an implementation.
2. Ask whether this detail is blocking the current build.
3. If it is not blocking, move it to the Curiosity Parking Lot.
4. State the smallest concrete implementation I should do next.
5. Help me define a short finish line: a working example, a test, a benchmark, a reproducible failure, or a shipped feature.

Suggested interruption:

> This is an interesting deep dive, but is it necessary to complete the current implementation? Capture it in the Curiosity Parking Lot. Let's build the smallest working version now, then return to this question if the implementation makes it relevant.

Do not discourage deep understanding. Redirect it toward purposeful investigation and delivery.

## Topic documentation

For each topic, maintain two primary documents:

- **Deep-Dive.md** — the problem, mental model, principles, internals, trade-offs, connections, and parked questions.
- **Implementation.md** — the working goal, design, code, tests, experiments, failures, run instructions, and evidence that it works.

The Deep-Dive document must not become an excuse to delay Implementation.md. Create both at the beginning of a topic. Keep the implementation document alive from the first coding session.

Use the templates in [templates/](templates/).

## Definition of done

A topic is not "done" merely because I read about it. A reasonable completion milestone is:

- I can explain the problem and mechanism without reading notes.
- I have independently built or modified a working example.
- I have tested at least one meaningful edge case or failure scenario.
- I can explain the trade-offs and when the approach is unsuitable.
- I have documented what I built, how to run it, and what I learned.
- I have committed the result.

Mastery can continue after this milestone. The point is to earn the right to move forward with a usable foundation, not to wait for perfect knowledge.

## A practical session

For a 90-minute session, use this as a starting point:

| Time | Activity |
|---|---|
| 20 min | Learn one bounded concept |
| 10 min | Recall and explain without notes |
| 40 min | Implement, test, or debug |
| 15 min | Document results and next steps |
| 5 min | Decide what to park and what to do next |

Adjust the timing for the task, but protect implementation time.

## Weekly reflection

At the end of a learning cycle, answer:

1. What did I build or ship?
2. How long did it take from first learning the concept to the first working implementation?
3. What did I understand incorrectly at first?
4. Which deep-dive questions actually improved the implementation?
5. Which questions were interesting but unnecessary for the current goal?
6. What is the next small capability I want to demonstrate?

## Personal reminder

**Understand enough to start. Build to understand more. Deep-dive with a reason. Ship what you learn.**
