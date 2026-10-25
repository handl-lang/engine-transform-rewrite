# How-to guides

Task recipes. Each assumes sibling checkouts of this repo and of the platform
repos it patches.

## Add a rewrite pass

Declare `TransformDef`s in the language/kit data and run them through `run_pass`; keep natives for what data cannot express.

## Write a native rule

Implement `NativeRewrite` and register it with `with_desugar_natives` (or your own set); rules stay addressable by name from data.
