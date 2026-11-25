# lib-math

Standard math **port types** — the math surface contracts (the port
side of the port/impl split). Backends `math-handl` (pure handl),
`math-c` (native `math.*` ops), and `math-js` (JS `Math`/`Number` via
the `js` ffi) implement these signatures.

## Layout

| path | role |
| --- | --- |
| `src/*.hnl` | one file per math arrow (`abs`, `add`, `ceil`, `factorial`, `gcd`, …) |
| `pkg.hnl` | manifest — `modules: ["math"]`, deps on `math-handl` + `math-c` |
| `scripts/hnl-gate.sh`, `workflows/gate.yaml` | the gate / bupha entry |

## Contract

- Pure `.hnl` contract package — no Rust crate, no `Cargo.toml`.
- The `.hnl` sources are gated by `hnl typecheck`/`lint`/`test`, not
  cargo.

## Verification

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

## License

MIT.

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
