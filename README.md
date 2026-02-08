# Achriom — Personal Librarian Plugin

A personal librarian plugin for [Cowork](https://claude.com/product/cowork), Anthropic's agentic desktop application — though it also works in Claude Code. Manages your media collection, analyzes what you read and watch, finds cross-media connections, and helps you decide what to pick up next.

## Installation

```
claude plugin marketplace add achriom/achriom-claude-plugin
claude plugin install achriom@achriom
```

## Quick Start

### 1. Install the plugin

Add the marketplace and install:

```
claude plugin marketplace add achriom/achriom-claude-plugin
claude plugin install achriom@achriom
```

### 2. Connect your collection

The plugin requires the Achriom MCP server. Add your API key to `.mcp.json` (included with the plugin) or configure in your Claude settings:

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

### 3. Start talking

The librarian activates automatically. Ask about your collection, request recommendations, or go deep on something you love.

## Commands

| Command | Description |
|---------|-------------|
| `/achriom:recommend` | Get a personalized recommendation based on mood, theme, or similarity |
| `/achriom:deep-dive` | Full analysis of a specific book, film, album, show, or anime |
| `/achriom:discover` | Trace a theme, mood, or idea across your entire collection |
| `/achriom:research` | Enter focused research mode on a curated subset of items |
| `/achriom:collection-review` | Full audit — patterns, taste profile, gaps, and what your library says about you |

## Skills

| Skill | Description |
|-------|-------------|
| `librarian` | Core persona — proactive, curious, demonstrates rather than describes |
| `book-analysis` | Literary deep-dives — themes, author context, passages, connections |
| `movie-analysis` | Film analysis — visual language, director style, cultural moment |
| `music-analysis` | Album discussion — sound, production, artist evolution, always plays tracks |
| `show-analysis` | TV series analysis — long-form storytelling, seasonal arcs, ensemble dynamics |
| `anime-analysis` | Animation-specific — studios, sakuga, adaptation fidelity, cultural context |
| `recommendations` | Cross-media recommendation methodology — mines your collection first |
| `collection-insights` | Pattern recognition — themes, taste evolution, gaps, collection personality |
| `focused-research` | Contained research mode — deep study of curated subsets |
| `stop-slop` | Always active — eliminates AI writing patterns from every response |

## Example Workflows

### Get a Recommendation

```
You: /achriom:recommend something cozy and soothing

Librarian: [Checks your collection, finds unread/unwatched items that match,
 plays a track preview from a matching album, embeds a trailer for a film,
 connects recommendations to things you've rated highly]
```

### Go Deep on Something

```
You: /achriom:deep-dive why is Kid A so divisive?

Librarian: [Pulls album details, plays tracks inline, finds video essays
 on YouTube, connects to other items in your collection that share DNA,
 incorporates your rating and notes]
```

### Trace a Theme

```
You: /achriom:discover found family

Librarian: [Searches across all media types, maps where the theme appears
 in books, films, albums, shows — finds cross-media connections,
 surfaces surprising pairings, identifies gaps]
```

### Focused Research

```
You: /achriom:research comparing my three Murakami novels

Librarian: [Enters contained mode, loads all three books, quotes passages,
 finds thematic overlaps and tensions, presents scholarly but
 accessible analysis]
```

### Full Collection Audit

```
You: /achriom:collection-review

Librarian: [Maps entire collection, identifies thematic throughlines,
 analyzes taste evolution, spots blind spots, builds a taste profile,
 suggests what to bump up the backlog queue]
```

### Natural Conversation

The librarian also works without commands — just talk:

- "What should I read next?" — recommendations skill activates
- "What makes Dune so good?" — book-analysis skill activates
- "Play something from OK Computer" — music-analysis skill plays tracks
- "What patterns do you see in my library?" — collection-insights skill activates

## Media Types

| Type | Source | Capabilities |
|------|--------|-------------|
| `book` | Open Library | Search, details, uploaded book content search |
| `movie` | TMDB | Search, details, YouTube video essays |
| `show` | TMDB | Search, details, cast interviews |
| `album` | Discogs + Apple Music | Search, details, track previews, live performances |
| `anime` | AniList | Search, details, openings, sakuga analysis |

## MCP Integration

> See [CONNECTORS.md](CONNECTORS.md) for the full list of tools provided by the Achriom MCP server.

The plugin connects to your collection through the Achriom MCP server, which provides 26 tools across collection management, search, ratings, behavioral intelligence, book content, media playback, and research mode.

The plugin works best with the MCP server connected. Without it, the librarian can still discuss media using its general knowledge, but cannot access your personal collection.

## File Structure

```
achriom/
├── .claude-plugin/
│   ├── plugin.json
│   └── marketplace.json
├── .mcp.json
├── README.md
├── CONNECTORS.md
├── commands/
│   ├── recommend.md
│   ├── deep-dive.md
│   ├── discover.md
│   ├── research.md
│   └── collection-review.md
└── skills/
    ├── librarian/SKILL.md
    ├── book-analysis/SKILL.md
    ├── movie-analysis/SKILL.md
    ├── music-analysis/SKILL.md
    ├── show-analysis/SKILL.md
    ├── anime-analysis/SKILL.md
    ├── recommendations/SKILL.md
    ├── collection-insights/SKILL.md
    ├── focused-research/SKILL.md
    └── stop-slop/SKILL.md
```
