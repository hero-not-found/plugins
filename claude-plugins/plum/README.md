# Plum for Claude Code

![Plum](assets/mark-light.png)

Recall conversations, find contacts, and summarize what matters from your Plum account.

MCP endpoint: `https://api.plum.hnf.dev/mcp`.

Use `/mcp` in Claude Code to authenticate this plugin's server. Each environment requires a separate connection.

Invoke `/plum:recall` to recall conversations.

The optional event channel is packaged at `channel/channel.mjs`. It reads the matching Plum account's `/events` API with an ordinary app bearer token; it does not use MCP OAuth credentials. Store the token outside this package. Create a separate MCP config whose stdio server runs `node` with the absolute path to `channel/channel.mjs`, then launch Claude with that config and `--dangerously-load-development-channels server:<your-server-name>`. Set either `PLUM_API_TOKEN` or `PLUM_API_TOKEN_FILE` in that session. The channel starts from the latest event and keeps its cursor only in memory. It is never enabled by installing this package alone. Keep the config and channel flag together: Claude may silently discard notifications without the flag even after the companion advances its in-memory cursor.
