<!--
Written by the sdlc release from sksizer/dev
(scripts/sdlc-mirror/templates/marketplace/README.md). An edit made here is replaced by the next
release; edit it in sksizer/dev.
-->

# osdlc marketplace

This repository is a plugin marketplace for Claude Code, Codex, Cursor and Pi. It publishes two
plugins, `sdlc` and `craft`.

It is generated and publish-only. Nothing here is edited by hand: the plugins are developed in
[sksizer/dev](https://github.com/sksizer/dev) and [osdlc/osdlc](https://github.com/osdlc/osdlc),
and each release replaces the contents of this repository. Open issues and pull requests against
osdlc/osdlc.

- `sdlc` (CLI and plugin): captures the work of building software, such as roadmaps, milestones
  and tasks, as markdown files with schema-checked frontmatter. It runs the workflows that move
  that work through its lifecycle.
- `craft` (plugin): portable skills for the software development lifecycle, with no scripts.
  `craft` works without `sdlc`, so you can install either plugin or both.

See [CHANGELOG.md](./CHANGELOG.md) for what each version shipped.

## Current version

**v0.18.0**

## Install

### Claude Code

```text
claude plugin marketplace add osdlc/marketplace
claude plugin install sdlc@osdlc
claude plugin install craft@osdlc
```

Inside a session the same steps read `/plugin marketplace add osdlc/marketplace`, then
`/plugin install sdlc@osdlc` and `/plugin install craft@osdlc`.

### Codex

Codex reads a marketplace manifest at `.agents/plugins/marketplace.json` in a repository root.
Point your Codex configuration at this repository to pick up both plugins. Use a local path once
cloned, or the remote-repository option your Codex CLI version supports.

### Cursor

Cursor reads a marketplace manifest at `.cursor-plugin/marketplace.json` in a repository root.
Point Cursor at this repository to pick up both plugins.

### Pi

Pi has no marketplace. Clone this repository and install each pack by path:

```text
pi install <clone>/.pi/packs/sdlc
pi install <clone>/.pi/packs/craft
```

Pi names each skill `<plugin>-<skill>` and runs it as `/skill:<plugin>-<skill>`, for example
`/skill:sdlc-task-work`.

## License

Apache-2.0 with an AI-training restriction (see [LICENSE](./LICENSE)). Because of the added
condition this is source-available, not OSI-approved open source. See also [NOTICE](./NOTICE).
