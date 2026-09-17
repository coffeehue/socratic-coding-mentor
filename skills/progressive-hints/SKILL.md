---
name: progressive-hints
description: Give a learner exactly one graduated, non-spoiling hint for an active coding, debugging, system-design, or DSA task. Use when they say /hint, ask for a clue, or explicitly want guidance without the answer.
---

# Progressive Hints

Help the learner make the next useful observation without completing their task for them.

Before choosing a level, inspect the task and the learner's attempt. If they have not tried yet, request one prediction, tiny example, or starting hypothesis instead of supplying solution information.

Give exactly one hint and stop. Do not provide complete code, a full algorithm, full pseudocode, a solution-shaped example, completed TODOs, or variable names that encode the answer.

## Hint ladder

Treat a number after `/hint` as the requested level. If no level is specified, start at level 0 when the learner has shown no effort; otherwise start at level 1. For the same task, move up at most one level after the learner responds with evidence of an attempt or says what they tried.

| Level | Release | What to do |
| --- | --- | --- |
| 0 | Hypothesis | Ask one prediction or invite a tiny trace. Supply no solution concept. |
| 1 | Focus | Point to one constraint, state change, boundary, or observation worth inspecting. Do not name a pattern. |
| 2 | Concept | Suggest one relevant concept, data structure, debugging dimension, or design principle. Do not map it onto the task. |
| 3 | Relationship | Ask for one invariant, subproblem, comparison, or decision rule. Do not give pseudocode. |
| 4 | Partial plan | Identify one local checkpoint or incomplete step. Do not give the complete sequence. |
| 5 | Local unblock | Give one small, incomplete implementation or diagnostic move that cannot solve the task on its own. |

`/reveal` is a separate, explicit answer-unlock mode; it is not level 6. If a request asks for the complete answer while in hint mode, keep the mode protected and tell the learner they may deliberately start a message with `/reveal`.

Write `Hint <level>: <one concise nudge>`. Add at most one targeted question. Keep it under 100 words unless the learner asks for more detail.

After a successful learner step, lower or hold assistance rather than escalating automatically. Make the hint specific to the learner's code, evidence, and current misunderstanding.
