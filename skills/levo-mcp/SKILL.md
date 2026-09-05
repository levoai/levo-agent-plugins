---
visibility: product-public
triggers:
  - User asks about their API applications or services tracked by Levo
  - User wants to list or explore API endpoints
  - User needs application details from Levo API catalog
  - User mentions Levo MCP, Levo API security, or API observability
---

# Levo MCP

Query the Levo API catalog using MCP tools. This skill provides access to your API inventory, application details, and endpoint information through the Levo MCP server.

## Prerequisites

- Levo MCP server configured in your MCP client
- Valid Levo.ai account with API applications

## Available Tools

### levo_list_applications

List all API applications (services) tracked by Levo.

**Use when:** User wants to see all their monitored APIs or services.

**Example prompts:**
- "List all my API applications"
- "What services does Levo track?"
- "Show me my API inventory"

### levo_get_application_details_by_name

Get detailed information about a specific application by name.

**Parameters:**
- `name` (required): The application name

**Use when:** User wants details about a specific service.

**Example prompts:**
- "Show me details for the payments-service"
- "What do you know about my user-api application?"
- "Get info on the orders service"

### levo_list_application_endpoints

List all endpoints for a given application.

**Parameters:**
- `application_name` (required): The application name

**Use when:** User wants to see API endpoints for a service.

**Example prompts:**
- "List endpoints for payments-service"
- "What APIs does the user-service expose?"
- "Show me all routes in the orders application"

## Workflow Examples

### Discovery Flow

1. Start by listing applications with `levo_list_applications`
2. Select an application of interest
3. Get details with `levo_get_application_details_by_name`
4. Explore endpoints with `levo_list_application_endpoints`

### Quick Endpoint Check

```
User: "What endpoints does my auth-service have?"

Agent:
1. Call levo_list_application_endpoints(application_name="auth-service")
2. Present the endpoint list with methods and paths
```

## Error Handling

| Error | Cause | Resolution |
|-------|-------|------------|
| Application not found | Name doesn't match | Use `levo_list_applications` to find correct name |
| Authentication failed | MCP not configured | Follow levo-getting-started skill |
| No applications | Empty catalog | Ensure Levo sensor is capturing traffic |

## Tips

- Application names are case-sensitive
- Use the exact name from `levo_list_applications` output
- Endpoints include HTTP method, path, and discovery source
