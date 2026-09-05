---
visibility: product-public
triggers:
  - User wants to set up or install Levo MCP
  - User asks how to connect to Levo
  - User has MCP authentication or connection issues with Levo
  - User is new to Levo and needs onboarding help
---

# Levo Getting Started

Install and connect to the Levo MCP server. This skill guides you through the setup process to enable Levo API security tools in your AI assistant.

## Prerequisites

- A Levo.ai account ([sign up free](https://levo.ai))
- An MCP-compatible client:
  - Claude Desktop
  - Cursor
  - VS Code with Claude extension

## Installation

### Step 1: Configure MCP Client

Add the Levo MCP server to your client's configuration file.

#### Claude Desktop

Edit `~/.config/claude/claude_desktop_config.json` (Linux/macOS) or `%APPDATA%\Claude\claude_desktop_config.json` (Windows):

```json
{
  "mcpServers": {
    "levo": {
      "url": "https://api.levo.ai/mcp",
      "transport": "streamable-http"
    }
  }
}
```

#### Cursor

Edit `.cursor/mcp.json` in your project or `~/.cursor/mcp.json` globally:

```json
{
  "mcpServers": {
    "levo": {
      "url": "https://api.levo.ai/mcp",
      "transport": "streamable-http"
    }
  }
}
```

### Step 2: Restart Your Client

After saving the configuration:
1. Fully quit your MCP client
2. Relaunch the application
3. The Levo server should appear in your MCP integrations

### Step 3: Authenticate

On first tool use:
1. You'll be prompted to authenticate
2. Sign in with your Levo.ai credentials
3. Authorize the MCP connection

## Verify Connection

Test the connection by asking:

> "List my Levo applications"

This should call `levo_list_applications` and return your API inventory.

## Troubleshooting

### Connection Failed

**Symptoms:** MCP client can't reach Levo server

**Solutions:**
1. Verify internet connectivity
2. Check the URL is exactly `https://api.levo.ai/mcp`
3. Ensure no proxy is blocking the connection
4. Try restarting your MCP client

### Authentication Issues

**Symptoms:** "Unauthorized" or "Authentication required" errors

**Solutions:**
1. Sign in again at [app.levo.ai](https://app.levo.ai)
2. Clear cached MCP credentials in your client
3. Verify your Levo account is active

### Server Not Appearing

**Symptoms:** Levo not listed in MCP integrations

**Solutions:**
1. Check JSON syntax in config file
2. Ensure the config file is in the correct location
3. Fully restart (not just reload) your client
4. Check client logs for configuration errors

### No Applications Found

**Symptoms:** `levo_list_applications` returns empty

**This is normal if:**
- You haven't deployed the Levo sensor yet
- No API traffic has been captured
- You're using a new Levo account

**Next steps:**
1. Visit [docs.levo.ai](https://docs.levo.ai) for sensor setup
2. Deploy sensor in your environment
3. Generate some API traffic
4. Applications will appear automatically

## Available Tools

Once connected, you'll have access to:

| Tool | Description |
|------|-------------|
| `levo_list_applications` | List all tracked API applications |
| `levo_get_application_details_by_name` | Get details for a specific app |
| `levo_list_application_endpoints` | List endpoints for an application |

## Next Steps

After successful setup:
1. Explore your API catalog with `levo_list_applications`
2. Investigate specific services with `levo_get_application_details_by_name`
3. Review endpoints with `levo_list_application_endpoints`

See the [levo-mcp skill](../levo-mcp/SKILL.md) for detailed tool usage.

## Support

- **Documentation:** [docs.levo.ai](https://docs.levo.ai)
- **Support:** support@levo.ai
- **Community:** [GitHub Discussions](https://github.com/levoai/levo-agent-plugins/discussions)
