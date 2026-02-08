# Connectors

## Achriom MCP Server (Required)

The core connection to your media collection. Provides 26 tools for search, management, analysis, and playback.

**Setup:** Add your API key to `.mcp.json`:

```json
{
  "mcpServers": {
    "achriom": {
      "type": "http",
      "url": "https://mcp.achriom.com/mcp?api_key=YOUR_ACHRIOM_API_KEY"
    }
  }
}
```

Get your API key at [achriom.com](https://achriom.com).

### Tools Provided

| Category | Tools | Purpose |
|----------|-------|---------|
| Core CRUD | `add_item`, `delete_item`, `edit_item`, `re_enrich` | Manage your collection |
| Search & Discovery | `search`, `lookup_item`, `get_details`, `get_stats`, `random_pick` | Find and explore items |
| Status & Ratings | `update_status`, `update_rating`, `update_notes`, `bulk_update_status`, `get_by_status`, `get_by_rating` | Track what you've read/watched/listened to |
| Behavioral Intelligence | `get_timeline`, `get_signals`, `get_context` | Understand your patterns |
| Book Content | `search_book_content`, `read_book_section` | Search and quote from uploaded books |
| Media Playback | `get_track_previews`, `preview_album`, `search_youtube` | Play music and embed video |
| Research Mode | `get_scope_info`, `expand_research_scope` | Focused research on subsets |
| Navigation | `show_item` | Open items in the app |
| Memory | `search_conversations` | Reference past conversations |

## Optional Enrichment

Plugin skills reference web search for additional context (author interviews, production history, critical reception). This works through any available web search capability — no additional configuration required.
