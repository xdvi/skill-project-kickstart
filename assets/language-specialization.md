# Language specialization (dynamic)

Generic core stays stack-agnostic. Load specialization only after detecting the project's language/stack. Do NOT hardcode one language here; when a new stack appears, record its conventions in the table.

## How to select

1. Detect stack from operator input, repo manifest (`go.mod`, `package.json`, `pyproject.toml`, `Cargo.toml`, ...), or ask.
2. Look up the row below. If missing, research current conventions online and add a row.
3. Apply ONLY that row's conventions. Never import another stack's rules.

## Specialization table

| Stack | Manifest | Test runner | Deps policy | Artifact dir |
|---|---|---|---|---|
| Go | `go.mod` (floor set by operator) | `go test ./...` | stdlib first; deps need reason | `internal/`, `cmd/` |
| TypeScript/Node | `package.json` | one runner, pinned | lockfile committed; deps minimal | `src/`, `tests/` |
| Python | `pyproject.toml` | one runner (pytest/uv) | pinned; venv isolated | `src/`, `tests/` |
| Rust | `Cargo.toml` | `cargo test` | crates.io minimal | `src/` |

## Rules

- Floor/toolchain version comes from operator or current stable, never invented.
- Bench/measurement artifacts go where the stack puts them (e.g. `bench/` for Go, `benchmarks/` otherwise).
- Names, comments, and commit style follow the stack's idioms (not another stack's).
- If conventions conflict with operator instructions, operator wins; record the deviation.

## Adding a stack

Append a row only after researching current official docs. One row, no prose.
