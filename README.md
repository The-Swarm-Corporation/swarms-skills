# Swarms Marketplace skills and plugin

<p align="left">
  <a href="https://skills.sh/The-Swarm-Corporation/swarms-skills"><img src="https://img.shields.io/badge/skills.sh-npx%20skills%20add-F5070C?style=for-the-badge&amp;labelColor=0A0A0A" alt="skills.sh"></a>
  <a href="https://swarms.world/mcp-skill.md"><img src="https://img.shields.io/badge/MCP-swarms.world%2Fmcp-F5070C?style=for-the-badge&amp;labelColor=0A0A0A&amp;logo=modelcontextprotocol&amp;logoColor=white" alt="MCP server"></a>
  <a href="https://insiders.vscode.dev/redirect/mcp/install?name=swarms-marketplace&amp;config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A//swarms.world/mcp%22%2C%22headers%22%3A%7B%22Authorization%22%3A%22Bearer%20%24%7Binput%3Aswarms_api_key%7D%22%7D%7D&amp;inputs=%5B%7B%22type%22%3A%22promptString%22%2C%22id%22%3A%22swarms_api_key%22%2C%22description%22%3A%22Swarms%20API%20key%20%28https%3A//swarms.world/platform/api-keys%29%22%2C%22password%22%3Atrue%7D%5D"><img src="https://img.shields.io/badge/VS%20Code-Install%20MCP-007ACC?style=for-the-badge&amp;labelColor=0A0A0A" alt="Install in VS Code"></a>
  <a href="https://swarms.world"><img src="https://img.shields.io/badge/Website-swarms.world-F5070C?style=for-the-badge&amp;labelColor=0A0A0A&amp;logo=googlechrome&amp;logoColor=white" alt="Website"></a>
  <a href="https://discord.gg/EamjgSaEQf"><img src="https://img.shields.io/badge/Discord-Join-5865F2?style=for-the-badge&amp;labelColor=0A0A0A&amp;logo=discord&amp;logoColor=white" alt="Discord"></a>
</p>

Agent skills and a plugin for the [Swarms Marketplace](https://swarms.world): search, read, publish and review AI agents, prompts, tools and MCP servers from your coding agent.

The Swarms Marketplace is where developers discover, share and monetize ready-made AI agents, prompts, tools and MCP servers. With these skills installed, your agent can find a listing for the job at hand, read its details, pricing and reviews, and publish or update your own products without leaving your editor. Everything runs through the marketplace's MCP server at `https://swarms.world/mcp` and its REST API. It works with Claude Code, Codex, VS Code, Cursor and any agent that supports [skills.sh](https://skills.sh).

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

### VS Code

Click **Install in VS Code** above. VS Code asks for your Swarms API key the first time the server starts.

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

## Join our community

Questions, feedback or ideas for new skills? Come say hi.

| Platform | Link |
| --- | --- |
| Discord | [discord.gg/EamjgSaEQf](https://discord.gg/EamjgSaEQf) |
| X | [@swarms_corp](https://x.com/swarms_corp) |
| YouTube | [Swarms](https://www.youtube.com/channel/UC9yXyitkbU_WSy7bd_41SqQ) |
| LinkedIn | [The Swarm Corporation](https://linkedin.com/company/The-Swarm-Corporation) |
| GitHub | [kyegomez/swarms](https://github.com/kyegomez/swarms) |
| Website | [swarms.world](https://swarms.world) |
| Docs | [docs.swarms.ai](https://docs.swarms.ai) |
