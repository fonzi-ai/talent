# Fonzi Talent

Fonzi matches exceptional engineers with AI startups and high-growth tech
companies. Apply once. Companies that want to meet you send an Interview
Request with the role, base salary, and context upfront. You approve every
meeting. Fonzi is free for engineers.

This repository packages Fonzi Talent for the agents you already use. It
connects to the Fonzi Talent MCP server at https://talent.fonzi.ai/mcp and
ships the skills that teach your agent how to use it. Sign-in is LinkedIn,
Google, or a magic link. There is no password.

Hiring teams want [Fonzi Recruiter](https://github.com/fonzi-ai/recruiter).

## Install

**Claude Code**

```sh
/plugin marketplace add fonzi-ai/plugins
/plugin install talent@fonzi
```

The `fonzi` marketplace lives at
[fonzi-ai/plugins](https://github.com/fonzi-ai/plugins) and lists both Fonzi
plugins. Adding it once is enough for either.

**Codex and ChatGPT**

Fonzi Talent is submitted to the plugin directory. Until it is listed, add
[fonzi-ai/plugins](https://github.com/fonzi-ai/plugins) as a marketplace from
the Plugins tab.

**Cursor**

Fonzi Talent is submitted to the Cursor Marketplace. For local use, clone this
repository into `~/.cursor/plugins/local/`.

**skills.sh**

```sh
npx skills add fonzi-ai/talent
```

Installs every skill in this repository. Connect the MCP server in your agent
separately; the skills tell the agent how.

## Layout

```
plugin.json                        Agent Plugins manifest (Codex, ChatGPT, Cursor)
mcp.json                           Agent Plugins MCP config
.claude-plugin/plugin.json         Claude Code manifest
.mcp.json                          Claude Code MCP config
skills/<name>/SKILL.md             Shared by every host
assets/                            Fonzi mark, source and 512px
scripts/check.sh                   Validates every format above
```

Skills are the shared asset. Every host reads the same `SKILL.md` files. The
manifest and MCP files exist in two dialects because Claude Code reads its own
format and Codex, ChatGPT, and Cursor read the open
[Agent Plugins](https://agent-plugins.org) standard. Marketplace files live in
[fonzi-ai/plugins](https://github.com/fonzi-ai/plugins), which points here.

## Contributing

- The plugin id `talent` is a permanent identifier across every directory. Do
  not rename it.
- Keep both dialects of the manifest and MCP file in sync.
- Bump `version` in both manifests when the plugin changes. Directory listings
  re-review on every release.
- Run `scripts/check.sh` before opening a pull request.

## Links

- Docs: https://talent.fonzi.ai/mcp/docs
- Support: https://fonzi.ai/support
- Privacy: https://fonzi.ai/privacy
