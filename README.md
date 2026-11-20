# lib-math

Standard math port types (the math surface contracts).

## Layout

```text
src/        the .hnl sources
pkg.hnl     package manifest — modules, deps, description, license
```

Dependencies: see `pkg.hnl`

## Gate

The `.hnl` sources are not covered by `cargo`; `hnl typecheck` / `lint` /
`test` is their gate, run in CI and available locally:

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

## License

MIT.
