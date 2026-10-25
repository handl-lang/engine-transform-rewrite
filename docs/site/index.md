# engine-transform-rewrite

The rule-interpreting transform engine (ADR-0094).

## What it is

The first `TransformEngine` implementation: it walks a pass's `TransformDef`s
bottom-up over the `Ast` arena with a `remap` old→new index table — the proven
`apply_desugar` algorithm generalised to any named pass. Dispatch is a
`kind → Vec<TransformDef>` table built once per pass; there are no `kind ==`
checks in the engine core.

## Start here

- **Reference** — [public API](/engine-transform-rewrite/reference/)
- **How-to** — [task recipes](/engine-transform-rewrite/how-to/)
- **Explanation** — [design and rationale](/engine-transform-rewrite/explanation/)

No tutorials: this repo is a building block used from Rust. End-to-end
walkthroughs live with the product that composes it — see the
[Handl platform](/handl/).
