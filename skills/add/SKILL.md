---
name: add
description: Fast library intake. Add books, movies, albums, shows, anime, podcasts, or games you name, with correct identification and optional status in one pass
argument-hint: "<titles, or 'I just finished X'>"
allowed-tools:
  - mcp__plugin_achriom_achriom__lookup_item
  - mcp__plugin_achriom_achriom__add_item
  - mcp__plugin_achriom_achriom__bulk_add_items
  - mcp__plugin_achriom_achriom__update_status
  - mcp__plugin_achriom_achriom__set_progress
  - mcp__plugin_achriom_achriom__mark_tv_watched
  - mcp__plugin_achriom_achriom__update_rating
  - mcp__plugin_achriom_achriom__get_stats
---

# /add: Build the Library Fast

Turn whatever the user names into correctly identified library entries, with minimum friction and no lost momentum.

## Invocation

```
/add Piranesi, In Rainbows, and the movie Arrival
/add I just finished Project Hail Mary, loved it
/add everything I mentioned above
```

## Workflow

### Step 1: Collect and Identify

Gather everything named, including works mentioned earlier in the conversation when the user says "these" or "what I mentioned."

- Three or fewer items: `lookup_item(media_type, title)` per item, then `add_item` with the returned external_id for an exact match.
- Four or more: `bulk_add_items`.

Media types: book, movie, album, show, anime, podcast, game. Use anime for Japanese animation and show for live-action or Western series. For games, `add_item` also accepts `platform` (the hardware they own it on) and `format` (physical or digital); pass them whenever the user mentions either.

### Step 2: Disambiguate Only When It Matters

Ask ONE quick question when the wrong match would genuinely hurt (remakes, common titles, same-name works by different creators). Never stall a ten-item intake on one ambiguous title: add the nine, flag the one.

### Step 3: Carry the Context

If they mentioned status or feeling alongside ("finished it last week," "halfway through," "loved it"), set it in the same pass:

```
update_status(media_type, title, status)
set_progress(...)            # partway through a book
mark_tv_watched(...)         # episodes watched
update_rating(...)           # when they volunteered a verdict
```

### Step 4: Confirm, Then Notice

Confirm compactly: what was added, one line. Then, once five or more items exist in the library, name ONE real pattern forming across them: a recurring theme, era, or sensibility. One specific observation, not a summary. This is the moment the collection starts to feel understood.

Never analyze patterns from fewer than three items; there is not enough signal.

## Voice

Efficient and warm. The confirmation is short; the observation is the payoff.
