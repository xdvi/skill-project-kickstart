---
name: project-kickstart
description: "Trigger: project kickstart, new project, sprint zero, walking skeleton, bootstrap standard. Researches current practices, offers architectures with tiny examples, then builds minimal standard phases."
license: Apache-2.0
metadata:
  author: "dabi"
  version: "2.0"
---

## Activation Contract

Load when operator starts a new project, asks for a standard bootstrap, sprint zero, walking skeleton, or initial architecture/rules.
Do not load for single fixes, task reviews, or status-only reporting.

## Hard Rules

- Research first: run targeted web searches on current architectures, patterns, and practices for THIS project type before proposing anything.
- Never decide architecture unilaterally. Present 2-3 alternatives, each with ONE tiny concrete example (<=8 lines), and ask the operator to choose. STOP and wait.
- Core stays generic. Language/stack specifics live in `assets/language-specialization.md`, selected dynamically. No language names in this file.
- Token economy: input is cheap, output is expensive. Synthesize only decision-relevant findings; tables over prose; never dump research verbatim.
- No unrequested boilerplate. Every file maps to a task or a requirement. Minimal viable scaffold only.
- TDD per task: failing test first, minimal code to pass.
- Chat in operator natural language. Code, docs, commits, evidence in English.

## Decision Gates

| Situation | Action |
|---|---|
| High uncertainty | Time-boxed spike first, throwaway allowed |
| Flow spans layers | Thin walking skeleton end-to-end |
| External dependency | Mock first, record fixtures |
| Performance claim | Baseline before optimizing |
| Architecture choice open | Alternatives + tiny examples + ask operator |
| Phase output untestable | Stop, split phase, do not advance |

## Execution Steps

1. Detect stack and project type; load specialization from `assets/language-specialization.md`.
2. Research current practices (web). Synthesize findings into one compact table.
3. Propose 2-3 architecture alternatives with tiny examples. Ask operator to choose. STOP.
4. Bootstrap minimal scaffold: manifest, build file, README, docs. Nothing more.
5. Build phases in order: mock skeleton -> full flow -> driver + baseline -> results record.
6. Emit status table after each phase (`assets/phases-template.md`).

## Output Contract

Return:
- Compact research summary (table) plus the alternatives presented.
- Operator's recorded choice.
- Files per phase with passing tests; no unrequested files.
- Reproducible results with commands, numbers, env, caveats.
- Status table after each phase and a single next-step line.

## References

- `assets/language-specialization.md` — dynamic stack specialization.
- `assets/phases-template.md` — phase checklist and table shape.
- `assets/decision-template.md` — alternatives format with tiny examples.
