# Redlands Plus MCP

Search local businesses in Redland City, Queensland, Australia (Cleveland, Capalaba, Victoria Point, Redland Bay, Wellington Point and the bay islands) from Cursor or any MCP client, powered by the [Redlands Plus](https://redlandsplus.com.au) directory. The server is streamable HTTP at `https://redlandsplus.com.au/mcp`.

## Tools

### `search_businesses`

Search approved public Redlands Plus listings by name, category, suburb, or a plain-English service query.

| Param | Type | Required | Description |
| --- | --- | --- | --- |
| `query` | string | yes | Search text, 1–200 characters. For example: `find a plumber in Capalaba`. |
| `limit` | integer | no | Maximum results. From 1 to 50. Defaults to 10. |

### `get_business`

Read one approved public listing using its UUID or the slug from its Redlands Plus listing URL. Supply exactly one of `id` or `slug`.

| Param | Type | Required | Description |
| --- | --- | --- | --- |
| `id` | string (UUID) | one of `id` or `slug` | Listing UUID. |
| `slug` | string | one of `id` or `slug` | Slug from the listing URL. Lowercase letters, digits, and single hyphens, 1–240 characters. |

## Install in Cursor

Use this config. The same file is at the repo root as `.mcp.json`.

```json
{
  "mcpServers": {
    "redlands-plus": {
      "url": "https://redlandsplus.com.au/mcp"
    }
  }
}
```

Put it in `~/.cursor/mcp.json` to use the server in every project, or in a project's `.cursor/mcp.json` to use it only there.

## Example prompts

- find a plumber in Capalaba
- cafes in Cleveland

## Notes

The server is read-only, needs no API key, and returns public listings only.
