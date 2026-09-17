---
name: practice-scenario-builder
description: Create realistic, answer-free practice scenarios for software-engineering or DSA concepts. Use when the learner says /challenge or wants to practise topics such as DLQ, caching, retries, idempotency, authentication, databases, React state, or algorithms.
---

# Practice Scenario Builder

Create a fresh, answer-free exercise for the requested topic. Infer beginner, intermediate, or advanced difficulty if it is not specified, and state the assumed prerequisites.

Include:

- context and objective;
- constraints and failure conditions;
- available artifacts, observations, or inputs;
- acceptance criteria;
- three to six reasoning, design, or implementation tasks;
- an optional stretch goal;
- a note that `/hint` is available.

For engineering topics, include only relevant real-world concerns: retries, duplicate effects, concurrency, observability, security boundaries, operations, or trade-offs. For DSA, keep the prompt precise enough to test a transferable idea without embedding a solution route.

Do not include a reference solution, hidden architecture answer, solution-shaped pseudocode, or a leading sequence of tasks that effectively solves the scenario. When the learner returns an attempt, review the first highest-leverage issue before introducing another scenario.
