# holocron-lsp

[![CI](https://github.com/holocron-lang/holocron-lsp/actions/workflows/ci.yml/badge.svg)](https://github.com/holocron-lang/holocron-lsp/actions/workflows/ci.yml)
[![crates.io](https://img.shields.io/crates/v/holocron-lsp.svg)](https://crates.io/crates/holocron-lsp)
[![docs.rs](https://img.shields.io/docsrs/holocron-lsp)](https://docs.rs/holocron-lsp)
[![license](https://img.shields.io/crates/l/holocron-lsp.svg)](LICENSE)

> The LSP server for [Holocron](https://github.com/holocron-lang/holocron) —
> a declarative schema and query compiler. Publishes live diagnostics for
> `.holocron.yaml` files with the same rustc-style messages you'd see from
> the CLI.

## Install

```sh
cargo install holocron-lsp
```

Or grab a prebuilt binary from the
[latest release](https://github.com/holocron-lang/holocron-lsp/releases/latest)
(macOS Intel + Apple Silicon, Linux x86_64 + ARM64, Windows x86_64).

## Editor integration

`holocron-lsp` is a stdio LSP server. Point your editor at the binary and
associate it with `*.holocron.yaml` files. Unknown columns, duplicate
aliases, unknown types, etc. underline in real time, pointing at the exact
YAML token at fault.

### Zed (project `.zed/settings.json`)

```json
{
  "lsp": {
    "holocron": {
      "binary": {
        "path": "/path/to/holocron-lsp",
        "arguments": []
      }
    }
  },
  "languages": {
    "YAML": { "language_servers": ["holocron"] }
  }
}
```

Make sure the worktree is **trusted** in Zed (otherwise project settings
are ignored).

### JetBrains (RustRover, IntelliJ, …) via LSP4IJ

1. Install the **LSP4IJ** plugin from the Marketplace.
2. `Settings → Languages & Frameworks → Language Servers → +` (New Language Server).
3. **Command:** the path to `holocron-lsp`.
4. **Mappings tab → File name patterns:** `*.holocron.yaml`.
5. **Language Id:** leave empty.

### Other editors

Any LSP client works. Point at the binary, associate the pattern.

## Development

This crate depends on [`holocron`](https://crates.io/crates/holocron). It's
released independently on its own cadence; bumps happen via Conventional
Commits and cocogitto in the same way as the parent project.

```sh
cargo build      # build
cargo test       # run tests
cargo doc --open # build & view the docs
```

[pre-commit](https://pre-commit.com) hooks mirror CI:

```sh
pre-commit install --install-hooks --hook-type commit-msg
```

## License

Licensed under the [Mozilla Public License 2.0](LICENSE).