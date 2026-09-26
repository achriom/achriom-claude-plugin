# Achriom

The media memory layer for AI agents and their humans. Books, movies, albums, TV shows, anime, podcasts, and games, tracked, analyzed, and searchable from Claude, ChatGPT, or any MCP client.

**48 tools** · **20 skills** (9 you can call by name) · **7 media types** · **Free for all accounts**

---

## Claude Plugin (Recommended)

The full librarian experience, skills and your collection, in one install.

### Install

In **claude.ai** or **Claude Desktop**: go to **Settings**, then **Plugins**, click **Add plugins**, and paste this URL:

```
https://github.com/achriom/achriom-claude-plugin.git
```

Sign in with your Achriom account when prompted. No API keys or manual config needed.

### What you get

**Skills**: activated automatically by the librarian based on context:

| Skill | When it activates |
|-------|-------------------|
| `librarian` | Every conversation about your collection |
| `book-analysis` | Literary analysis and author deep-dives |
| `movie-analysis` | Film craft, directors, cinematography |
| `music-analysis` | Albums, sound, production |
| `show-analysis` | Series structure, seasonal arcs, ensemble dynamics |
| `anime-analysis` | Studios, sakuga, adaptation, cultural context |
| `games-analysis` | Design, systems, developers, franchises, playtime |
| `recommendations` | "What should I read/watch/play next?" questions |
| `collection-insights` | Pattern recognition across your full library |
| `focused-research` | Deep study on a curated subset of items |
| `stop-slop` | Writing quality filter, always on |

**Skills you can call by name** (type them, or just ask in your own words):

| Command | Description |
|---------|-------------|
| `/achriom:recommend` | Personalized recommendation by mood, theme, or similarity |
| `/achriom:deep-dive` | Full analysis of a specific book, film, album, show, anime, podcast, or game |
| `/achriom:discover` | Trace a theme or idea across your entire collection |
| `/achriom:research` | Focused deep-study mode on a curated subset |
| `/achriom:collection-review` | Full library audit, patterns, taste profile, gaps |
| `/achriom:add` | Fast intake of whatever you name, identified correctly |
| `/achriom:watched` | Log what you watched with dates: episodes, rewatches, where you left off |
| `/achriom:lists` | Save, read, and edit curated cross-media lists |
| `/achriom:portrait` | Your Taste Portrait, read back to you |

---

## Claude.ai Connector (Tools Only)

MCP tools without the librarian skills.

1. Open **Settings** and go to **Connectors**
2. Click **Add** and choose **Add custom connector**
3. Enter a name (e.g. Achriom) and paste the URL below
4. Click **Add**, then **Connect** to sign in with your Achriom account

```
https://mcp.achriom.com/mcp
```

No API key needed, authentication is handled via OAuth.

---

## ChatGPT

Install the official Achriom app from the [ChatGPT app store](https://chatgpt.com/apps/achriom/asdk_app_698a63a87aa081918a6532ccf4cbc1a1).

---

## Other MCP Clients

Any MCP client that connects to remote servers with OAuth (Claude Code, Cursor, and others) can use the same URL and sign in with your Achriom account:

```
https://mcp.achriom.com/mcp
```

In Claude Code: `claude mcp add --transport http achriom https://mcp.achriom.com/mcp`, then sign in when prompted.

---

## What the Tools Do

- **Search**: by title, creator, genre, theme, mood, or rating, in one media type or across all seven by meaning
- **Item details**: full metadata with AI analysis and your notes
- **Collection stats**: patterns across ratings, genres, themes, eras
- **Read and write**: update ratings, status, notes, format, priority, and progress from any client
- **Lists**: build named cross-media lists, add and remove items, read them back in order. Lists are private, and the Achriom app can turn one into a share link
- **Games**: platforms, developer, franchise, game modes, time to beat, and a play status of its own (unplayed, playing, played, saved, on hold, abandoned)
- **Edit and delete**: correct metadata, remove items, re-fetch AI analysis
- **Recommendations**: what people with overlapping taste also keep, across all media or seeded from one title you own, drawn from other libraries in aggregate and never anyone's individual list
- **A dated diary**: log finishes and re-reads, rewatches, and re-listens with dates (a year alone is kept as a year), set or fix started, finished, and added dates, and backfill up to 250 entries in one call
- **Undo**: clear a rating, delete a logged event
- **Recently added**: your library in the order you added it
- **Exact matching**: every tool that acts on one item takes its id as well as its title; an ambiguous title returns the candidates and changes nothing
- **Bulk operations**: add or update multiple items at once
- **Random pick**: let the librarian choose something from your collection
- **Apple Music previews**: 30-second samples inline
- **YouTube search**: trailers, interviews, video essays
- **Book search**: semantic search inside uploaded EPUBs and PDFs

Metadata sources: Open Library for books, TMDB for movies, TVDB for shows, Discogs for albums, AniList for anime, and IGDB for games. Games metadata is powered by IGDB.com.

---

## Try It

Three prompts that show the core of it (with a few items in your library):

1. **Build and read the library:** "Add Piranesi, In Rainbows and the film Arrival, then tell me what those three have in common."
2. **Recommendations with a reason:** "/achriom:recommend something like Blade Runner, but a book."
3. **A dated diary:** "I rewatched Heat last night and finished The Wire back in 2019. Log both, then show me my last five additions."

More: "/achriom:deep-dive OK Computer", "/achriom:discover memory across everything I own", "/achriom:lists start a list called Rainy Sunday with Paterson and Blue Velvet", "/achriom:watched where was I on Severance?"

## Troubleshooting

- **The tools do not appear.** Open Settings, then Connectors (or Plugins) and check Achriom shows as connected. If not, remove it and add it again, then sign in.
- **"Authentication required" or a sign-in loop.** Sign out of the connector and connect again; the sign-in is your Achriom account (Apple, Google or email).
- **A title lands on the wrong edition or film.** Ask the librarian to look it up first ("look up Dune, the 1984 film"). When a title is ambiguous the tools return the candidates and change nothing; say which one you meant.
- **Something still does not work.** Write to [hello@achriom.com](mailto:hello@achriom.com) with what you asked and roughly when.

## Privacy and Support

- **Privacy policy:** [achriom.com/privacy](https://achriom.com/privacy). The connector reads and writes only your own Achriom library. It does not read your Claude conversations, memory or files; it sees only what Claude sends in a tool call.
- **Terms:** [achriom.com/terms](https://achriom.com/terms)
- **Support and security reports:** [hello@achriom.com](mailto:hello@achriom.com)

## Requirements

Free Achriom account required. MCP access is included on every plan. The monthly cap applies to librarian chat inside the Achriom app: 10 messages on Free, 200 on Pro.

[Sign up](https://app.achriom.com/login) · [Settings](https://app.achriom.com/settings) · [Support](mailto:hello@achriom.com)

---

## Find Us

- [Smithery](https://smithery.ai/servers/achriom/achriom)
- [Glama](https://glama.ai/mcp/connectors/com.achriom.mcp/achriom)
- [MCP.so](https://mcp.so/server/achriom/achriom)
