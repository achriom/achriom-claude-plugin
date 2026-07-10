---
name: portrait
description: Present your Taste Portrait, Achriom's synthesized reading of who you are through what you collect
argument-hint: "(no arguments)"
allowed-tools:
  - mcp__plugin_achriom_achriom__get_taste_portrait
  - mcp__plugin_achriom_achriom__get_stats
  - mcp__plugin_achriom_achriom__get_signals
  - mcp__plugin_achriom_achriom__search
---

# /portrait: Your Taste, Read Back to You

Deliver Achriom's synthesized reading of the user's taste as a moment, not a data dump.

## Invocation

```
/portrait
/portrait what does my library say about me
```

## Workflow

### Step 1: Fetch the Portrait

```
get_taste_portrait()
```

If a portrait exists, present it faithfully: the archetype, the through-lines, the tensions. Quote its language rather than paraphrasing it flat. The portrait was written by a librarian who read everything they own; honor that voice.

### Step 2: If No Portrait Exists

Do not fake one. Check the library:

```
get_stats()
```

If the library is thin (under roughly 15 items), say the portrait needs a few more items to be worth writing, and offer to help build the collection. If the library is substantial, the portrait is still being written; say so and offer a first impression from the stats instead, clearly labeled as a glance, not the portrait.

### Step 3: One Thread to Pull

After presenting, offer ONE concrete follow-up drawn from the portrait: a dormant thread worth returning to, or a gap the portrait implies. Make it specific:

```
get_signals()
search(media_type, query="a theme the portrait names")
```

## Voice

This is a mirror, not a report card. Present observations with warmth and specificity. Never invent traits the portrait does not contain.
