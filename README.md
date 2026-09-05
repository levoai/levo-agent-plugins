# Levo Agent Plugins

[![CI](https://github.com/levoai/levo-agent-plugins/actions/workflows/ci.yml/badge.svg)](https://github.com/levoai/levo-agent-plugins/actions/workflows/ci.yml)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)

Public Levo agent plugins for Claude, Cursor, and AI coding assistants.

## Overview

This repository contains skills (plugins) that enable AI agents to interact with [Levo.ai](https://levo.ai) — the API security and observability platform. These skills use the Levo MCP (Model Context Protocol) server to provide secure, governed access to API security data.

## Available Skills

| Skill | Description |
|-------|-------------|
| [levo-mcp](skills/levo-mcp/SKILL.md) | Query Levo API catalog using MCP tools |
| [levo-getting-started](skills/levo-getting-started/SKILL.md) | Install and connect to Levo MCP server |

## Quick Start

### Prerequisites

- A Levo.ai account ([sign up free](https://levo.ai))
- An MCP-compatible AI client (Claude Desktop, Cursor, VS Code with Claude extension)

### Installation

1. **Configure your MCP client** with the Levo server:

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

2. **Authenticate** when prompted by your MCP client

3. **Start using** Levo tools in your AI assistant

### Example Usage

Ask your AI assistant:

> "List all my API applications tracked by Levo"

> "Show me the endpoints for my payments-service application"

> "What APIs does my user-service expose?"

## MCP Tools

These skills expose the following Levo MCP tools:

| Tool | Description |
|------|-------------|
| `levo_list_applications` | List all API applications (services) tracked by Levo |
| `levo_get_application_details_by_name` | Get detailed information about a specific application |
| `levo_list_application_endpoints` | List all endpoints for a given application |

## Documentation

- [Getting Started Guide](skills/levo-getting-started/SKILL.md)
- [MCP Tool Reference](skills/levo-mcp/SKILL.md)
- [Classification Guidelines](docs/CLASSIFICATION.md)
- [Contributing](CONTRIBUTING.md)
- [Security Policy](SECURITY.md)

## Contributing

We welcome contributions! Please read our [Contributing Guide](CONTRIBUTING.md) and [CLA](CLA.md) before submitting a PR.

## License

This project is licensed under the Apache License 2.0 — see the [LICENSE](LICENSE) file for details.

## Support

- **Documentation:** [docs.levo.ai](https://docs.levo.ai)
- **Issues:** [GitHub Issues](https://github.com/levoai/levo-agent-plugins/issues)
- **Email:** support@levo.ai

---

Built with ❤️ by [Levo.ai](https://levo.ai)
