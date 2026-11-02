# Swarms Marketplace skills and plugin

Agent skills and a plugin for the [Swarms Marketplace](https://swarms.world): search, read, publish and review AI agents, prompts, tools and MCP servers from your coding agent.

| Skill | What it covers |
| --- | --- |
| [`swarms-marketplace-api`](skills/swarms-marketplace-api/SKILL.md) | The Swarms Marketplace REST API: agents, prompts, tokenization and fee claims. |
| [`swarms-marketplace-mcp`](skills/swarms-marketplace-mcp/SKILL.md) | The Swarms Marketplace MCP server at `https://swarms.world/mcp`: connecting, auth, and the full tool catalog. |

The plugin bundles both skills with the MCP server. Calling a tool needs a Swarms API key from [swarms.world/platform/api-keys](https://swarms.world/platform/api-keys).

## Install

### Any agent (skills.sh)

```bash
npx skills add The-Swarm-Corporation/swarms-skills
```

### Claude Code

```
/plugin marketplace add The-Swarm-Corporation/swarms-skills
/plugin install swarms-marketplace@swarms
```

Claude Code asks for your Swarms API key when the plugin is enabled and stores it in your system's secure credential store.

### Codex

```bash
codex plugin marketplace add The-Swarm-Corporation/swarms-skills
```

Then install **Swarms Marketplace** from the plugin list and enter your Swarms API key when asked.

### MCP server only

Any MCP client that supports Streamable HTTP can connect directly:

```bash
claude mcp add --transport http swarms https://swarms.world/mcp \
  --header "Authorization: Bearer $SWARMS_API_KEY"
```

See the [MCP skill](skills/swarms-marketplace-mcp/SKILL.md) for Cursor, Claude Desktop and SDK setups.

## Layout

| Path | Read by |
| --- | --- |
| `skills/*/SKILL.md` | skills.sh, Claude Code and Codex |
| `.claude-plugin/plugin.json`, `.claude-plugin/marketplace.json`, `.mcp.json` | Claude Code |
| `plugin.json`, `mcp.json`, `.agents/plugins/marketplace.json` | Codex |

## Links

- Marketplace: https://swarms.world
- Developer docs: https://swarms.world/developers
- OpenAPI: https://swarms.world/openapi.json
- llms.txt: https://swarms.world/llms.txt

## License

Apache-2.0. See [LICENSE](LICENSE).
