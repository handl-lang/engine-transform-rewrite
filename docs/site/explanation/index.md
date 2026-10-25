# Explanation

## Why this crate exists

The desugarer was a one-off; most later passes had the same shape (bottom-up,
remap, replace root). Generalising it into an engine turned passes into data and
let kits compose them, while natives stayed the escape hatch for host-side
operations.

## Where it sits

This crate belongs to the `engine-*` family. Plugins, kits and hosts reach it
through the kit's operation slot, so the engine can be swapped without touching a
language definition.

See the [reference](/engine-transform-rewrite/reference/) for the API and the
[how-to guides](/engine-transform-rewrite/how-to/) for tasks.
