# Phases template

Default shape (English). Localize headers and status phrases to operator language.
Phases are generic; naming adapts to project type (web, CLI, service, lib).

## Phase checklist

- [ ] P0 bootstrap: manifest, build file, README, docs
- [ ] P1 minimal slice: one happy path end-to-end, smoke test
- [ ] P2 full flow: all steps, per-id state, latency/cost flag, request log
- [ ] P3 driver + baseline: sequential runs, timing, resource, results
- [ ] P4 results: commands, numbers, env, caveats

## Table shape

```markdown
| Task | Status |
|---|---|
| P0 bootstrap | ✅ done — `SHA` |
| P1 minimal slice | ✅ done — `SHA` |
| P2 full flow | 🚀 running (`branch`) |
| P3 baseline | ⏳ pending |
| P4 results | ⏳ pending |
```

## Rules
- Each phase: one testable deliverable + commit.
- Measure before optimizing (P3 before any perf claim).
- Names come from the plan; keep them verbatim in the table.
