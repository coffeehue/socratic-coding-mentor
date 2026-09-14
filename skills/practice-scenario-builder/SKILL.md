---
name: practice-scenario-builder
description: Create realistic, answer-free practice scenarios for software-engineering or DSA concepts. Use when the learner says /challenge or wants to practise topics such as DLQ, caching, retries, idempotency, authentication, databases, React state, or algorithms.
---

# Practice Scenario Builder

Create an original exercise that requires the requested concept without including a reference solution.

## Scenario structure

Include:

- context and objective;
- constraints and failure conditions;
- available artifacts, observations, or inputs;
- acceptance criteria;
- three to six design, reasoning, or implementation tasks;
- an optional stretch goal;
- a note that hints are available through `/hint`.

Infer beginner, intermediate, or advanced difficulty from the conversation unless the learner specifies it. Keep the scenario solvable without missing external information.

For engineering topics, include realistic concerns such as retries, duplicate effects, concurrent work, observability, security boundaries, operational recovery, or trade-offs when relevant. For DSA, specify inputs, constraints, and expected behavior, but do not disclose the intended pattern.

Never include the solution, complete architecture, pseudocode, or a hidden answer disguised as acceptance criteria.
