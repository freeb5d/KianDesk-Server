# KianDesk Server Program

[<a href="docs/README-FA.md">فارسی</a>] | [<a href="docs/README-AR.md">العربية</a>] | [<a href="docs/README-ZH.md">中文</a>]

Self-host your own KianDesk server.

## How to build manually

```bash
cargo build --release
```

Three executables will be generated in target/release.

- hbbs - KianDesk ID/Rendezvous server
- hbbr - KianDesk relay server
- rustdesk-utils - KianDesk CLI utilities

You can find updated binaries on the [Releases](https://github.com/freeb5d/KianDesk-Server/releases) page.

## Configuration

`hbbs` and `hbbr` can be configured with command-line flags, environment
variables, or an `.env` / config file. Run `hbbs --help` or `hbbr --help` to see
the available flags.

The most common options:

| Option | Flag | Env var | Applies to | Purpose |
| --- | --- | --- | --- | --- |
| Key | `-k` | `KEY` | hbbs, hbbr | `hbbs` loads/generates one by default |
| Bind address | `-b` | `BIND` | hbbs, hbbr | Local IP address to listen on (default: all interfaces; requires 1.1.17+) |
| Port | `-p` | `PORT` | hbbs, hbbr | Listening port (hbbs `21116`, hbbr `21117`) |
| Relay servers | `-r` | `RELAY-SERVERS` | hbbs | Override when the relay uses a different address or a non-standard port |
| Force relay | — | `ALWAYS_USE_RELAY` | hbbs | `Y` disables direct connections |
| Log level | — | `RUST_LOG` | hbbs, hbbr | e.g. `debug` (default `info`) |

See **[docs/environment-variables.md](docs/environment-variables.md)** for the
full list of variables, the file/flag/env precedence rules, database and relay
bandwidth tuning, Docker image variables, and examples.

## Installation

Please follow this [doc](https://rustdesk.com/docs/en/self-host/rustdesk-server-oss/)
