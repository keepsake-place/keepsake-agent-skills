# Keepsake Agent Skills

Give your AI agent a memory that lasts: ideas, tasks and the people who matter.

## What is this?

[Keepsake](https://keepsake.place) (keepsake.place) is the app where creators and solo entrepreneurs empty their heads: ideas, tasks and the people who matter, together and linked in one place, all the way to publishing. This skill teaches AI agents how to use Keepsake effectively — when to log interactions, how to organize contacts, and how to build a knowledge base.

## Quick Start

1. **Create your account** at [app.keepsake.place](https://app.keepsake.place/register)
2. **Install this repository as a plugin** in Grok Bot or Cursor. See [Install as a plugin](#install-as-a-plugin-grok-bot-cursor). On first connect, sign in with your Keepsake account.
3. **No plugin client?** Copy `skills/keepsake-crm/SKILL.md` to your agent's skills directory, then generate an API key in Settings → Connections → API keys and Claude.

## Install as a plugin (Grok Bot, Cursor)

This repository is also a plugin for the Grok Bot and Cursor plugin marketplaces. It bundles:

- **The hosted Keepsake MCP server** (`.mcp.json`) — `https://app.keepsake.place/api/mcp`, 87 tools, Streamable HTTP.
- **The `keepsake-crm` skill** (`skills/keepsake-crm/`) — teaches your agent how to use Keepsake well.

Manifests: `.grok-plugin/plugin.json` and `.cursor-plugin/plugin.json`. Logo: `assets/logo.png`.

On first use, your client opens the Keepsake sign-in page (OAuth 2.1 with PKCE). Approve access and you're connected — no API key to copy. You need a Keepsake account ([start a 30-day free trial](https://app.keepsake.place/register)).

### Network endpoints and credentials

| Endpoint | Why |
|---|---|
| `https://app.keepsake.place/api/mcp` | The MCP server the plugin connects to |
| `https://app.keepsake.place/oauth/authorize`, `/api/oauth/token`, `/api/oauth/register` | OAuth sign-in (discovered via `/.well-known/oauth-protected-resource` and `/.well-known/oauth-authorization-server`) |

- **Credentials:** an OAuth access token for your own Keepsake account (scope `mcp`), stored by your client. Clients without OAuth can send a personal API key (`ksk_…`, Settings → Connections → API keys and Claude) as `Authorization: Bearer`.
- **Data access:** only your own account. Writes made through the API appear in API Activity inside Keepsake.
- **No hooks, no scripts, no local code execution.** The plugin is configuration and Markdown only.

## What the skill teaches your agent

- 🧠 **The 3-dimension model** — Time, People, and Themes
- 📝 **Log interactions** — Calls, meetings, emails linked to the right people
- ✅ **Track follow-ups** — Tasks with due dates, recurrence, and contact links
- 📋 **Capture knowledge** — Notes as digital index cards, organized by project
- 🔍 **Search everything** — Global search for idea collisions and resurfacing connections

## Also available

- **MCP Server**: `npx -y keepsake-mcp` — 87 native tools for Claude, Cursor, and any MCP client ([npm](https://www.npmjs.com/package/keepsake-mcp))
- **REST API**: Full HTTP API for custom integrations ([documentation](https://keepsake.place/en/api))

## Links

- [Keepsake website](https://keepsake.place)
- [API documentation](https://keepsake.place/en/api)
- [AI integration guide](https://keepsake.place/en/ai)
- [MCP server on npm](https://www.npmjs.com/package/keepsake-mcp)

## License

MIT — see [LICENSE](LICENSE)
