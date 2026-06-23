# holocron-lsp

LSP server for [Holocron](https://github.com/holocron-lang/holocron) — a
declarative schema and query compiler. Publishes live diagnostics for
`.holocron.yaml` files with the same rustc-style messages you'd get from
the CLI.

## Status

🚧 **Scaffolding in progress.** The LSP server existed inside the main
`holocron` crate up through v0.3.0; this repo is the home for it going
forward. First release here will be v0.1.0 once the holocron 0.4.0
release (which removes the bin from the parent crate) lands on crates.io.

## Install (once released)

```sh
cargo install holocron-lsp
```

Or download a prebuilt binary from the
[latest release](https://github.com/holocron-lang/holocron-lsp/releases/latest).

## License

[MPL-2.0](LICENSE) — matches the parent project.