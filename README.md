# engine-transform-rewrite

`hnl-engine-transform-rewrite` — The first [`TransformEngine`] implementation (ADR-0094): a rule-interpreting rewriting engine that generalizes the legacy `handl-runtime::desugar_pass` machinery.

## Development

```bash
cargo fmt --check && cargo clippy --all-targets -- -D warnings && cargo test
```

`ci.sh` is the gate (fmt → clippy → test → doc). Deps resolve from git, so no
sibling checkouts are needed; a plain clone test-runs as-is.

## License

MIT.

## Documentation

Published site (Diátaxis): <https://handl-lang.github.io/docs/engine-transform-rewrite/>

- [Reference](https://handl-lang.github.io/docs/engine-transform-rewrite/reference/) — public API surface
- [How-to](https://handl-lang.github.io/docs/engine-transform-rewrite/how-to/) — task recipes
- [Explanation](https://handl-lang.github.io/docs/engine-transform-rewrite/explanation/) — design and rationale

Decision records live on the `project` branch under `project/adrs/`.
