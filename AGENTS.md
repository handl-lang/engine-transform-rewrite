# Agent guide — tool-transform-rewrite

`hnl-tool-transform-rewrite` — the first `TransformEngine`
implementation (ADR-0094): a rule-interpreting rewriting engine that
generalizes the legacy `handl-runtime::desugar_pass` machinery. Passes,
pipelines, and plans are interpreted from `lang.transforms` data over
the `Term`/AST IR. `publish = false` (git-install only). Rust 2024.

## Layout

| path | role |
| --- | --- |
| `src/lib.rs` | crate docs + `TransformEngine` impl entry |
| `src/step.rs`, `src/dispatch.rs`, `src/walk.rs` | rule steps, dispatch, tree walk |
| `src/native/mod.rs`, `src/native/desugar.rs` | native (Rust-side) transform steps |
| `tests/` | `engine`, `desugar_parity` (parity vs legacy desugar) |
| `benches/`, `docs/` | benchmarks + engine doc |
| `xtask/`, `workflows/gate.yaml`, `bupha.toml`, `.cargo/` | vendored repo gate + CI wiring |

## Contract

- Deps resolve from git — `handl-language`/`handl-value` →
  `handl-lang/kernel`, `hnl-tool-transform` → sibling repo,
  `handl-runtime` → `handl-lang/host`, all `branch = "main"`.
- `desugar_parity` is the correctness anchor: rewrite output must match
  the legacy `desugar_pass` — keep it green when touching `native/`.

## Verification

```bash
cargo xtask gate   # fmt --check → clippy -D warnings → test → doc
```


<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->
