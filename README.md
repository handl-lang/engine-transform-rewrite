# engine-transform-rewrite

`hnl-engine-transform-rewrite` — the first `TransformEngine` implementation: a
rule-interpreting rewriting engine that generalizes the legacy
`handl-runtime::desugar_pass` machinery.

An `engine-*` crate: a concrete transform engine — passes, pipelines, and
plans are interpreted from `lang.transforms` data over the `Term`/AST IR.

## Development

```bash
cargo xtask gate        # fmt --check → clippy -D warnings → test → doc
```

`cargo xtask` wraps the repo's `xtask/` crate (`fmt`, `clippy`, `test`, `doc`,
`check`, `gate`); `ci.sh` is the gate entry. Deps resolve from git, so no
sibling checkouts are needed; a plain clone test-runs as-is.

## License

MIT.

## Documentation

<https://handl-lang.github.io/docs/engine-transform-rewrite/>
