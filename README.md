# flo2-connector plugins

One plugin marketplace for the flo2 family. Add it once to Claude Code or Grok Build, and you can install any of the
plugins listed below. Each plugin lives in its own repository and is released there. This repository only lists
them, each one pinned to an exact commit.

## Add the marketplace

Claude Code:

```sh
claude plugin marketplace add flo2-connector/plugins
claude plugin install flo2-cad@flo2-connector
```

Grok Build. Grok names the marketplace after the repository, `plugins`, and asks you to confirm a plugin that runs
programs:

```sh
grok plugin marketplace add flo2-connector/plugins
grok plugin install flo2-cad@plugins --trust
```

`claude plugin update` and `grok plugin update` move you to whatever this marketplace pins next.

## The plugins

| Plugin | What it does | Repository |
|---|---|---|
| `flo2-cad` | Designs casting-ready jewelry with an agent. A ring is given a named size and a prong or bezel head. Every piece is checked against cited casting limits before any STL or 3MF is released. | [flo2-connector/flo2-cad](https://github.com/flo2-connector/flo2-cad) |
| `flo2-ifc` | IfcOpenShell's ifcmcp, the MCP server for IFC building models. It loads, queries, edits, validates, quantifies and plots a building model. | [flo2-connector/flo2-ifc](https://github.com/flo2-connector/flo2-ifc) |

`reflow2` and `flo2` join this list once their own plugins are released.

These plugins run on your own machine. To use them through a chat app (claude.ai, grok.com, ChatGPT), with your
designs kept for you, connect [flo2.io](https://flo2.io) instead. flo2.io runs the same helpers.

## How a plugin is listed

`.claude-plugin/marketplace.json` lists each plugin as a source in its own repository:

```json
{ "source": "url", "url": "https://github.com/flo2-connector/<repo>.git", "sha": "<full commit sha>" }
```

Claude Code and Grok Build both read this file. To move a plugin to a new release, change its `sha` to the
released commit. Then check the file with `claude plugin validate .` and open a pull request.

## Licence

Apache-2.0. Each plugin carries its own licence in its own repository.
