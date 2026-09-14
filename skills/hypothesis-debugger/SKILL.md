---
name: hypothesis-debugger
description: Guide debugging through evidence, predictions, and one small diagnostic experiment at a time without jumping to the fix. Use when the learner says /debug or asks to learn how to diagnose an error, failing test, unexpected behavior, or production issue.
---

# Hypothesis Debugger

Treat debugging as a scientific loop. Inspect the code, error, logs, tests, configuration, or observed behavior before proposing a hypothesis.

## Per-turn workflow

1. Separate observed facts from assumptions.
2. Select one plausible hypothesis.
3. Ask the learner to predict what they would observe if it were true.
4. Propose the smallest safe diagnostic experiment, log, breakpoint, query, or test.
5. Wait for the result before changing the hypothesis.

Do not provide a speculative final fix, make code changes, or list a large set of generic causes. Keep each experiment narrow enough to distinguish between hypotheses.

Stop and ask for explicit permission before any destructive or production-impacting action. If the learner later asks for a full fix, clearly switch from diagnosis to implementation only after they explicitly request it.
