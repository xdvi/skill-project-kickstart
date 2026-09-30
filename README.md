# skill-project-kickstart

A reusable agent skill that turns "start a new project" into a disciplined, low-boilerplate, decision-driven workflow — for any language or stack.

## The problem

New projects often start as a mess: arbitrary architecture, unrequested boilerplate, and instant tech debt. An AI handed "build X" will happily invent structure nobody chose. This skill makes the kickoff step a **standardization, architecture, and decision layer** instead.

## How it works

1. **Detect** the stack and load its conventions dynamically (`assets/language-specialization.md`). No language is hardcoded in the core.
2. **Research** current architectures, patterns, and practices on the web before proposing anything.
3. **Offer alternatives** — 2-3 options, each with one tiny concrete example (≤8 lines) and its trade-off. The operator picks. Never decided unilaterally.
4. **Build minimal**: scaffold only what a task requires. TDD. No boilerplate by default.
5. **Report** a compact status table after each phase.

It optimizes for cheap input and expensive output: the agent researches and synthesizes only what's decision-relevant, instead of dumping reams of unnecessary content.

## Files

| File | Role |
|---|---|
| `SKILL.md` | The core, stack-agnostic contract |
| `assets/language-specialization.md` | Dynamic per-stack conventions (add a row, don't hardcode) |
| `assets/phases-template.md` | Generic phase checklist + status table shape |
| `assets/decision-template.md` | Alternatives format with tiny examples |

## Install

Clone into your skills directory (OpenCode, Claude Code, or compatible harness):

```bash
git clone https://github.com/xdvi/skill-project-kickstart.git ~/.config/opencode/skills/project-kickstart
```

The skill name comes from `SKILL.md` frontmatter (`project-kickstart`), not the folder name.

## Usage

Trigger phrases: "project kickstart", "new project", "sprint zero", "walking skeleton", "bootstrap standard".

The agent researches current practices, presents architecture alternatives with tiny examples, asks you to choose, then builds the minimal scaffold and reports progress phase by phase.

## License

Apache-2.0
