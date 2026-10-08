# Install SEO Audit by OpenKrill (for AI agents)

This is a hosted remote MCP server. There is nothing to clone, build or run locally.

1. Add a remote MCP server named `openkrill-seo-audit` with transport Streamable HTTP and URL `https://seoaudit.openkrill.app/mcp`.
   No API key, header or environment variable is needed.
2. Cline: run `cline mcp install openkrill-seo-audit --transport http https://seoaudit.openkrill.app/mcp`, or add this to `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "openkrill-seo-audit": {
      "type": "streamableHttp",
      "url": "https://seoaudit.openkrill.app/mcp",
      "disabled": false
    }
  }
}
```

3. Check the install by listing the server's tools. You should see the tools in the README.md table, for example `audit_site`.
