# Socratic Coding Mentor

An open learning system for coding, DSA, debugging, and software engineering. It helps learners reason and implement for themselves instead of receiving a finished solution by default.

## What it does

| Capability | Command | Learning behavior |
| --- | --- | --- |
| Progressive hints | `/hint [0-5]` | One graduated clue at a time; starts with a prediction when there is no attempt. |
| Socratic teaching | `/teach` or `/coach` | One focused question, then waits for the learner. |
| Concept lessons | `/explain` | Concept → mental model → mechanics → example → code → pitfalls → transfer check. |
| DSA foundations | `/foundations` or `/toolkit` | Maps prerequisites without spoiling the original exercise. |
| Applied practice | `/challenge [topic] [difficulty]` | Creates a realistic, answer-free scenario. |
| Learning review | `/review` | Identifies one evidence-backed, highest-leverage issue. |
| Evidence-led debugging | `/debug` | Tests one hypothesis with one small diagnostic step. |

The shared prompt also includes `/quiz`, `/reflect`, and `/reveal`. `/reveal` is the only deliberate mode that may provide a complete solution for the current task.

## Hint ladder

`/hint` is not a disguised solution generator. It uses six controlled levels:

| Level | Purpose |
| --- | --- |
| 0 | Ask for a prediction or tiny trace. |
| 1 | Focus attention on one constraint or behavior. |
| 2 | Name one relevant concept. |
| 3 | Explore one relationship, invariant, or decision rule. |
| 4 | Identify one incomplete local checkpoint. |
| 5 | Give one small local unblock that cannot finish the task alone. |

The mentor moves up only after the learner shows an attempt or evidence. `/reveal` is separate; it is not “hint level 6.”

## Use it

### ChatGPT Custom GPT

This is the best public ChatGPT route. In the GPT editor, paste [chatgpt-custom-gpt-instructions.md](prompts/chatgpt-custom-gpt-instructions.md) into **Instructions** (not the full master prompt; Custom GPT Instructions has a size limit). Enable only the capabilities you want; **Actions are not required**. Add the provided conversation starters, test the GPT, then choose the public sharing option available to your account.

### ChatGPT, Codex, Gemini, or Claude chat

Copy [master-system-prompt.md](prompts/master-system-prompt.md) into a project, Gem, custom instruction surface, or the first message of a new chat. This works as a portable fallback, but it does not install native skills or plugins.

### Claude skills

Download the individual ZIP packages from [dist/claude](dist/claude) and import them wherever your Claude account exposes skill import. Platform availability differs by plan and region; the prompt fallback above always works.

### Codex plugin

Install the plugin source at [plugins/socratic-coding-mentor](plugins/socratic-coding-mentor) in a Codex environment that supports local plugins. The packaged release is in [dist/openai](dist/openai).

For current click-by-click platform publishing instructions and limitations, see [PUBLIC_DISTRIBUTION_GUIDE.md](docs/PUBLIC_DISTRIBUTION_GUIDE.md).

## Examples

```text
/hint I am solving this array problem. I tried nested loops and it times out.
/teach Here is my retry handler and the duplicate-message bug I see: ...
/explain idempotency keys in TypeScript
/foundations [paste an unsolved DSA exercise]
/challenge event-driven architecture intermediate
/debug Expected one email; actual behavior is three emails. Here are the logs: ...
```

## Repository layout

```text
prompts/
  master-system-prompt.md              # Canonical unrestricted prompt
  chatgpt-custom-gpt-instructions.md   # Size-constrained Custom GPT version
skills/                                # Canonical portable skill packages
plugins/socratic-coding-mentor/        # Codex plugin and mirrored skills
dist/claude/                           # Individual skill ZIP release assets
dist/openai/                           # Plugin ZIP release assets
evals/behavior-cases.md                # Manual behavior and leakage checks
docs/                                  # Blueprint, publishing, privacy, terms
```

## Contributing and releasing

The canonical behavior starts in [master-system-prompt.md](prompts/master-system-prompt.md) and the seven folders under [skills](skills). When behavior changes:

1. Update the master prompt and the affected canonical skill package(s).
2. Keep the matching `plugins/socratic-coding-mentor/skills/` package byte-for-byte aligned.
3. Update the Custom GPT version so it preserves the same learning contract within its field limit.
4. Run the cases in [behavior-cases.md](evals/behavior-cases.md).
5. Regenerate the Claude and Codex ZIP assets and publish a new semantic-versioned release.

Do not silently weaken the anti-spoiler contract. Release notes should call out changes to `/reveal`, hint levels, or answer-leakage protections.

## License

[MIT](LICENSE)
