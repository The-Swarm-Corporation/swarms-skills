# Swarms Marketplace skills and plugin

<!-- Install -->
[![skills.sh](https://skills.sh/b/The-Swarm-Corporation/swarms-skills)](https://skills.sh/The-Swarm-Corporation/swarms-skills)
[![MCP server](https://img.shields.io/badge/MCP-swarms.world%2Fmcp-f5070c?style=flat&logo=modelcontextprotocol&logoColor=white)](https://swarms.world/mcp-skill.md)
[![Claude Code plugin](https://img.shields.io/badge/Claude%20Code-plugin-d97757?style=flat&logo=claude&logoColor=white)](#claude-code)
[![Codex plugin](https://img.shields.io/badge/Codex-plugin-000000?style=flat)](#codex)
[![Install in VS Code](https://img.shields.io/badge/VS%20Code-Install%20MCP-0098FF?style=flat)](https://insiders.vscode.dev/redirect/mcp/install?name=swarms-marketplace&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A//swarms.world/mcp%22%2C%22headers%22%3A%7B%22Authorization%22%3A%22Bearer%20%24%7Binput%3Aswarms_api_key%7D%22%7D%7D&inputs=%5B%7B%22type%22%3A%22promptString%22%2C%22id%22%3A%22swarms_api_key%22%2C%22description%22%3A%22Swarms%20API%20key%20%28https%3A//swarms.world/platform/api-keys%29%22%2C%22password%22%3Atrue%7D%5D)

<!-- Project -->
[![Website](https://img.shields.io/badge/website-swarms.world-f5070c?style=flat&logo=googlechrome&logoColor=white)](https://swarms.world)
[![Docs](https://img.shields.io/badge/docs-docs.swarms.ai-1f2937?style=flat&logo=readthedocs&logoColor=white)](https://docs.swarms.ai/docs/marketplace)
[![OpenAPI](https://img.shields.io/badge/OpenAPI-openapi.json-6BA539?style=flat&logo=openapiinitiative&logoColor=white)](https://swarms.world/openapi.json)
[![llms.txt](https://img.shields.io/badge/llms.txt-swarms.world-4b5563?style=flat)](https://swarms.world/llms.txt)
[![Get an API key](https://img.shields.io/badge/API%20key-get%20one-f5070c?style=flat)](https://swarms.world/platform/api-keys)
[![License](https://img.shields.io/github/license/The-Swarm-Corporation/swarms-skills?style=flat)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/The-Swarm-Corporation/swarms-skills?style=flat&logo=github)](https://github.com/The-Swarm-Corporation/swarms-skills/stargazers)

<!-- Community -->
[![Swarms framework](https://img.shields.io/github/stars/kyegomez/swarms?style=flat&logo=github&label=swarms)](https://github.com/kyegomez/swarms)
[![X](https://img.shields.io/badge/follow-%40swarms__corp-000000?style=flat&logo=x&logoColor=white)](https://x.com/swarms_corp)
[![Discord](https://img.shields.io/badge/Discord-join-5865F2?style=flat&logo=discord&logoColor=white)](https://discord.gg/EamjgSaEQf)
[![YouTube](https://img.shields.io/badge/YouTube-Swarms-FF0000?style=flat&logo=youtube&logoColor=white)](https://www.youtube.com/channel/UC9yXyitkbU_WSy7bd_41SqQ)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-The%20Swarm%20Corporation-0A66C2?style=flat)](https://linkedin.com/company/The-Swarm-Corporation)

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
