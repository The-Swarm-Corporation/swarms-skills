# Install the Swarms Marketplace MCP server in Cline

Follow these steps to add the Swarms Marketplace MCP server to Cline. The server is hosted at `https://swarms.world/mcp`. Do not install a local package.

## Step 1: Get a Swarms API key

Ask the user for a Swarms API key. The user creates a key at https://swarms.world/platform/api-keys.

Do not invent or guess a key. Wait until the user gives you the key.

## Step 2: Add the server to Cline

Open the Cline MCP settings file. In the Cline panel, open **MCP Servers**, then **Configure**, then **Configure MCP Servers**.

Add this entry under `mcpServers`:

```json
"swarms-marketplace": {
  "type": "streamableHttp",
  "url": "https://swarms.world/mcp",
  "headers": {
    "Authorization": "Bearer <SWARMS_API_KEY>"
  },
  "disabled": false,
  "autoApprove": []
}
```

Replace `<SWARMS_API_KEY>` with the key from Step 1. Keep the word `Bearer` and the space before the key.

Save the file. Cline reloads the server. If the server shows an error, check the key and the URL.

The CLI alternative is:

```bash
cline mcp add swarms-marketplace https://swarms.world/mcp --transport http --header "Authorization: Bearer <SWARMS_API_KEY>" --yes
```

## Step 3: Check that the server works

Call the MCP method `tools/list` on the server. The response is a list of tools. It includes `get_search`.

Call the tool `get_search` with this argument:

```json
{ "q": "research", "types": "agent", "limit": "3" }
```

The response is JSON with matching marketplace agents. A result is a success, even when the list is short.

If the call returns HTTP 401 or error `-32001`, the key is missing or wrong. Ask the user for the key again.

## What the server does

Use the server to search, read and review agents, prompts, tools and bundles on the Swarms Marketplace. With a key, the server can also publish and edit the user's own listings. Ask the user before you publish, edit or review anything.

The tool list is generated from https://swarms.world/openapi.json. The tool names can change. Call `tools/list` again when you need the current names.
