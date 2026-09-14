# Socratic Coding Mentor

An open, no-spoiler learning system for coding, DSA, debugging, and software engineering.

**Tagline:** Learn to solve it; don't outsource the thinking.

## What this includes

| Skill | Invoke with | Purpose |
| --- | --- | --- |
| Progressive Hints | `/hint` | One progressively stronger clue, never a solution dump |
| Socratic Teacher | `/teach`, `/coach` | One focused question at a time |
| Concept Explainer | `/explain` | Concept → mental model → example → code → pitfalls |
| DSA Foundations | `/foundations`, `/toolkit` | Learn prerequisites before an algorithmic problem |
| Practice Scenario Builder | `/challenge` | Create realistic, answer-free exercises such as DLQ scenarios |
| Learning Code Reviewer | `/review` | Find the first important issue without rewriting the code |
| Hypothesis Debugger | `/debug` | Debug through evidence and small experiments |

The master prompt also provides `/quiz`, `/reflect`, and `/reveal`. `/reveal` is the deliberate escape hatch for a complete solution.

## Repository layout

```text
prompts/master-system-prompt.md  # For Gemini Gems and instruction surfaces
skills/                          # Agent Skills source packages (SKILL.md)
dist/claude/                     # Upload-ready Claude ZIP releases
evals/behavior-cases.md          # Regression cases for anti-spoiler behavior
docs/BLUEPRINT.md                # Product and publishing design notes
```

## Use it

### Gemini

1. Open **Gems** in Gemini.
2. Create a Gem named **Socratic Coding Mentor**.
3. Paste the entire content of `prompts/master-system-prompt.md` into its instructions.
4. Add conversation starters such as `/hint`, `/teach`, `/foundations`, and `/challenge DLQ intermediate`.
5. Test before sharing.

### Claude

Each ZIP in `dist/claude/` contains one focused skill with a lowercase `skill.md`, which Claude expects.

1. In Claude, open **Customize → Skills**.
2. Upload one or more ZIP files from `dist/claude/`.
3. Enable the skills and test with the matching command.

Use the master prompt inside a Claude Project if you prefer one assistant with all commands in the same conversation.

### ChatGPT / Codex compatible skills

The source packages in `skills/` use the Agent Skills-style `SKILL.md` plus `agents/openai.yaml` metadata. Install or import them through the Skills surface available in your ChatGPT/Codex environment.

The Custom GPT route is not recommended for new personal public releases; use reusable skills or plugins where your account supports them.

## Public release checklist

1. Create a public GitHub repository from this folder.
2. Keep the MIT license unless you need different terms.
3. Create a GitHub release and attach the ZIPs in `dist/claude/`.
4. Publish your Gemini Gem using **Public** or **Anyone with the link**.
5. Do not include secrets, private code, or uploaded sensitive files. Shared Gem instructions and files can be visible to recipients.
6. Run `evals/behavior-cases.md` after every change. A learning mentor fails if it leaks a complete solution indirectly.


## Develop the skills

Each skill is intentionally narrow. Keep its `description` precise because compatible agents use it to decide when to activate the skill. Do not add README files inside individual skill folders.

When changing a skill, test both:

- prompts that should invoke it;
- prompts that should stay protected from answer leakage.

## License

MIT. See [LICENSE](LICENSE).
