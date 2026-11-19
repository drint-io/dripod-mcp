# Dripod MCP — 3D print-on-demand mockups

[![AllMCPs Verified](https://allmcps.com/api/badge/dripod)](https://allmcps.com/mcp/dripod?verify=48c7354b-71af-48d3-be6f-d1abe111ac9e)

**Dripod** puts a print-on-demand design on a product mockup and gives back a PNG for an Etsy, Shopify or Printify listing. The products are drawn in 3D with real light by Drint's render engine, the print following the folds of the fabric or the curve of the mug: 174 blanks on 9 shelves — T-shirts and tops, hoodies, mugs and tumblers, hats, totes and bags, phone and AirPods cases, pillows and towels, socks and aprons, jackets and pants. Every garment is worn on an invisible form, never a flat lay.

This repository holds the setup files for the **hosted** Dripod MCP server. There is nothing to install or run:

```
https://drint.io/dripod/mcp
```

- Transport: Streamable HTTP
- Sign-in: none. Pictures are up to 1024 px with a light watermark grid, about 20 an hour per address. Clean pictures up to 2048 px, every colour at once in marketplace sizes: [Dripod Pro](https://drint.io/dripod/pricing) on the website.
- Website: [drint.io/dripod](https://drint.io/dripod)

## Tools

| Tool | What it does |
|---|---|
| `list_products` | Dripod's products, each with its blank colours and its page on drint.io. Narrow it by shelf or by a word in the name |
| `pod_mockup` | A design (public https link, or base64 PNG / JPEG / WebP up to 10 MB; a transparent PNG works best) on one product in one colour, returned as a PNG (also as a link kept for an hour). Options: `colour`, `background` ("transparent" or a colour), `size` (512 or 1024) |

## Connect

### Claude (claude.ai, Claude Desktop)

Settings → Connectors → **Add custom connector** → URL `https://drint.io/dripod/mcp`.

### Claude Code

```bash
claude mcp add --transport http dripod https://drint.io/dripod/mcp
```

Or install it as a plugin from this repository:

```
/plugin marketplace add drint-io/dripod-mcp
/plugin install dripod@dripod
```

### ChatGPT

Settings → Apps & Connectors → Advanced → Developer mode → **Create** → MCP server URL `https://drint.io/dripod/mcp`, no authentication.

### Cursor

Add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "dripod": { "url": "https://drint.io/dripod/mcp" }
  }
}
```

### VS Code (GitHub Copilot)

Command Palette → **MCP: Add Server** → HTTP → `https://drint.io/dripod/mcp`. Or add to `.vscode/mcp.json`:

```json
{
  "servers": {
    "dripod": { "type": "http", "url": "https://drint.io/dripod/mcp" }
  }
}
```

### Gemini CLI

```bash
gemini extensions install https://github.com/drint-io/dripod-mcp
```

### Codex CLI

Add to `~/.codex/config.toml`:

```toml
[mcp_servers.dripod]
url = "https://drint.io/dripod/mcp"
```

### Windsurf, Cline, Kiro, goose and other clients

Use any "remote / Streamable HTTP server" option with the URL `https://drint.io/dripod/mcp`. No headers and no key are needed.

## Try it

- "Put my design on a black T-shirt and a white mug." (attach or link the design)
- "Which colours does the zip hoodie come in?"
- "Make a phone case mockup of https://example.com/design.png on a transparent background."

## Links

- Dripod: https://drint.io/dripod
- Support: support@drint.io
- Privacy Policy: https://drint.io/privacy (the picture link expires after an hour)
- Drint (packaging mockups and dielines), Drict (label-law checks) and Drisp (device mockups) have their own MCP servers: [drint-io/drint-mcp](https://github.com/drint-io/drint-mcp), [drint-io/drict-mcp](https://github.com/drint-io/drict-mcp), [drint-io/drisp-mcp](https://github.com/drint-io/drisp-mcp)

## License

The files in this repository are MIT-licensed. The drint.io service follows the [Drint Terms](https://drint.io/terms).
