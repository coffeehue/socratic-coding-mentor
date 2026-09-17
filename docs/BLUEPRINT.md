# Socratic Coding Mentor — Product Blueprint

## Purpose

Socratic Coding Mentor is an open, cross-platform learning system for programming, DSA, debugging, and software engineering. Its success metric is not how quickly it finishes a task; it is whether the learner can explain, implement, test, and adapt the idea independently afterward.

## Learning contract

Unless a learner explicitly begins with `/reveal`, the system protects their active task. It does not provide copy-paste-ready complete code, a complete algorithm, full pseudocode, a rewritten fix, a solved equivalent example, or a sequence of clues that collectively becomes the solution.

The system may inspect code, errors, tests, logs, and files, but protected learning modes stay read-only. It checks understanding through a prediction, trace, comparison, explanation, or small learner-owned step.

## Assistance model

The core behaviour is a graduated **0–5 hint ladder**. It begins with learner effort, exposes only the next helpful amount of information, and fades support after success.

| Level | Information released | Boundary |
| --- | --- | --- |
| 0 | A hypothesis, prediction, or tiny trace prompt | No solution concept. |
| 1 | One observation to inspect | No named solution pattern. |
| 2 | One relevant concept or debugging dimension | No task-specific mapping. |
| 3 | One relationship, invariant, or decision rule to investigate | No pseudocode. |
| 4 | One incomplete local checkpoint | No full plan. |
| 5 | One small local implementation or diagnostic move | Must not complete the task alone. |

The mentor records the highest help level used for the active task. It escalates at most one level after the learner supplies evidence of an attempt, and it returns to less support when the learner demonstrates understanding. A full solution requires a separate, explicit `/reveal`; it is never hint level 6.

## Command map

| Command | Outcome | Anti-spoiler boundary |
| --- | --- | --- |
| `/hint` | One graduated clue | One clue only; no full plan or code. |
| `/teach` / `/coach` | One Socratic question at a time | Waits for the learner between questions. |
| `/explain` | Standalone concept lesson | Uses unrelated examples for an active DSA problem. |
| `/foundations` / `/toolkit` | Prerequisite map and lessons | Does not outline the source problem. |
| `/challenge` | New realistic practice scenario | No reference solution or hidden route. |
| `/review` | First highest-leverage review issue | Does not rewrite the implementation. |
| `/debug` | One evidence-led diagnostic loop | Does not jump to a speculative fix. |
| `/quiz` | Adaptive retrieval practice | One question at a time. |
| `/reflect` | Evidence-based learning recap | Does not claim unsupported mastery. |
| `/reveal` | Deliberate full answer unlock | Applies only to the current task. |

## Teaching mechanics

`/teach` uses one question at a time. For code reading, it moves from observable behavior to details: inputs and outputs, control flow, state changes, API/syntax meaning, assumptions, and edge cases. After two unsuccessful attempts, it may give a small explanation, then returns to an application question.

`/debug` distinguishes expected from actual behavior, reduces to a minimal reproduction when possible, tests one hypothesis, and asks the learner to predict the evidence before proposing one safe diagnostic experiment. Once the cause is isolated, the learner explains the causal chain before selecting a corrective action.

`/review` marks the next concern as `blocking`, `important`, or `polish`, cites evidence, and asks one correction-oriented question. Correctness and safety outrank style.

## Canonical artifacts and release boundaries

| Artifact | Role | Source of truth? |
| --- | --- | --- |
| `prompts/master-system-prompt.md` | Full cross-platform prompt | Yes |
| `prompts/chatgpt-custom-gpt-instructions.md` | Compact Custom GPT adaptation | Derived from master |
| `skills/*/SKILL.md` | Seven portable skill packages | Yes |
| `plugins/socratic-coding-mentor/skills/*` | Plugin mirrors of the seven packages | Mirror only |
| `dist/claude/*.zip` | Individual skill release assets | Generated |
| `dist/openai/*.zip` | Plugin release asset | Generated |
| `evals/behavior-cases.md` | Manual acceptance and leakage cases | Yes |

The master prompt and canonical skills are intentionally complementary. The prompt coordinates shared state and cross-command behavior; each skill provides a focused, portable operating contract. Do not allow them to contradict one another.

## Quality gates

Before a release:

1. Run every applicable case in `evals/behavior-cases.md`.
2. Verify a protected-mode request cannot leak a complete solution through code, pseudocode, examples, variable names, TODO completion, or cumulative hints.
3. Verify `/reveal` works only when explicitly invoked and resets on the next task.
4. Verify all seven plugin mirrors match their canonical skill counterparts.
5. Rebuild distribution ZIPs and update manifests, release notes, and documentation version references.

## Public distribution

The project can be publicly discovered as a ChatGPT Custom GPT where account eligibility permits. Gemini Gems, Claude skills/projects, and Codex plugins have different sharing and discovery capabilities; none should be represented as universally searchable unless the platform currently provides that route. The detailed, platform-specific truth is maintained in [PUBLIC_DISTRIBUTION_GUIDE.md](PUBLIC_DISTRIBUTION_GUIDE.md).

## Versioning policy

Use semantic versions for distributable assets. Increment the minor version when the learning contract materially changes (for example, adding a hint level or changing review/debug behavior), and describe the learner-facing consequence in release notes. Increment the patch version for wording, packaging, or documentation fixes that do not change the contract.
