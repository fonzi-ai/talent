# Fonzi agent plugins

Fonzi is the world’s most connected recruiter, matching exceptional engineers
with AI startups and high-growth tech companies. This repository packages Fonzi
for the agents people already use.

Two plugins, one per audience:

| Plugin | For | MCP server |
| --- | --- | --- |
| [Fonzi Talent](plugins/talent) | Engineers looking for their next role | https://talent.fonzi.ai/mcp |
| [Fonzi Recruiter](plugins/recruiting) | Hiring teams working with Fonzi | https://recruiting.fonzi.ai/mcp |

Both servers use OAuth. The host opens Fonzi’s sign-in the first time a tool is
used. Sign-in is LinkedIn, Google, or a magic link. There is no password.

## Install

**Claude Code**

```sh
/plugin marketplace add kumospace/fonzi-agent-plugins
/plugin install fonzi-talent@fonzi
/plugin install fonzi-recruiter@fonzi
```

**Codex and ChatGPT**

Fonzi Talent and Fonzi Recruiter are submitted to the plugin directory. Until
they are listed, add this repository as a marketplace from the Plugins tab.

**Cursor**

Fonzi Talent and Fonzi Recruiter are submitted to the Cursor Marketplace. For
local use, clone this repository and point Cursor at `plugins/talent` or
`plugins/recruiting` from `~/.cursor/plugins/local/`.

**skills.sh**

```sh
npx skills add kumospace/fonzi-agent-plugins --skill fonzi-talent
npx skills add kumospace/fonzi-agent-plugins --skill fonzi-recruiter
```

## Layout

```
.claude-plugin/marketplace.json      Claude Code marketplace
.agents/plugins/marketplace.json     Codex and ChatGPT marketplace
plugins/<audience>/
  plugin.json                        Agent Plugins manifest (Codex, ChatGPT, Cursor)
  mcp.json                           Agent Plugins MCP config
  .claude-plugin/plugin.json         Claude Code manifest
  .mcp.json                          Claude Code MCP config
  skills/<name>/SKILL.md             Shared by every host
  assets/logo.png                    512px Fonzi mark for directory listings
assets/                              Source logo
scripts/check.sh                     Validates every format above
```

Skills are the shared asset. Every host reads the same `SKILL.md` files. The
manifest and MCP files exist in two dialects because Claude Code reads its own
format and Codex, ChatGPT, and Cursor read the open
[Agent Plugins](https://agent-plugins.org) standard.

## Contributing

- Plugin names (`fonzi-talent`, `fonzi-recruiter`) are permanent identifiers
  across every directory. Do not rename them.
- Keep both dialects of each manifest and MCP file in sync.
- Bump `version` in both manifests when a plugin changes. Directory listings
  re-review on every release.
- Run `scripts/check.sh` before opening a pull request.

## Links

- Talent docs: https://talent.fonzi.ai/mcp/docs
- Recruiter docs: https://recruiting.fonzi.ai/mcp/docs
- Support: https://fonzi.ai/support
- Privacy: https://fonzi.ai/privacy
