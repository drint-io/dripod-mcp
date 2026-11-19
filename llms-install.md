# Installing the Dripod MCP server

Dripod is a hosted MCP server. There is nothing to clone, build or install, it needs no API key, and there is no sign-in.

1. Add this entry to the MCP settings file (for Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "dripod": {
      "type": "streamableHttp",
      "url": "https://drint.io/dripod/mcp"
    }
  }
}
```

2. Check that it works: call `list_products`. It lists every product with its blank colours and its page.

3. To make a mockup, call `pod_mockup` with `product` (from `list_products`), optionally `colour`, and the design as `design_url` (public https) or `design_base64` (PNG, JPEG or WebP, up to 10 MB). It returns a PNG.

Docs: https://drint.io/dripod
