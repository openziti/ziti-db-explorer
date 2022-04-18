# ziti-db-explorer
OpenZiti controllers rely upon [bbolt](https://github.com/etcd-io/bbolt) for lightweight embedded data storage. A bbolt
database is a key value store where both keys and values are treated as opaque byte arrays. OpenZiti's 
[storage.boltz](https://github.com/openziti/storage) library adds types to the base bbolt implementation. While other
tools exist to explore raw bbolt database files, they do not know of OpenZiti's type system.

[//]: # (This tool is also included in the `ziti` CLI under `ziti db explore` in version 0.25.5 and later)

# Installation

> go install github.com/openziti/ziti-db-explorer/cmd/ziti-db-explorer/...@latest

# Building From Source

> git clone https://github.com/openziti/ziti-db-explorer.git
> go build ./...

# Installing from Source

> git clone https://github.com/openziti/ziti-db-explorer.git
> go install ./...

# Usage

```
'ziti-db-explorer' is an interactive shell for exploring Ziti Controller database files

Usage:
        ziti-db-explorer <ctrl.db> [-h]
```

# Commands

All commands support tab completion.

- `list [--skip x, --limit -y]` - list keys by skipping x and limiting to y
- `show <key>` - show the entire value of a key (long values are truncated)
- `back` - alternative to `cd ..`
- `cd <bucket>` - enter bucket
- `root` - return to the root bucket
- `clear` - clear the console