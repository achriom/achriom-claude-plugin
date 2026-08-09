---
name: lists
description: Curated cross-media lists. Save a grouping that came up in conversation, read back what is on a list, and keep lists accurate across books, movies, albums, shows, anime, podcasts, and games
argument-hint: "<list name, or 'save these as a list'>"
allowed-tools:
  - mcp__plugin_achriom_achriom__create_list
  - mcp__plugin_achriom_achriom__add_to_list
  - mcp__plugin_achriom_achriom__remove_from_list
  - mcp__plugin_achriom_achriom__get_list
  - mcp__plugin_achriom_achriom__lookup_item
  - mcp__plugin_achriom_achriom__add_item
  - mcp__plugin_achriom_achriom__search
---

# /lists: Keep the Groupings That Matter

A list is a mixtape for a collection: a handful of things from any media type, gathered because they belong together. Lists are private to the user and can be shared from the Achriom app with a private link.

## Invocation

```
/lists
/lists Halloween marathon
/lists save these as a list
/lists what's on my beach house list?
```

## When to Offer a List

Conversations produce groupings on their own. Someone plans a weekend, works through a director, or builds a stack for a trip. When four or five items have gathered around one idea, offer once, in a single line, and name the list you would make:

> "That's a list. Want me to save it as Sunday Melancholy?"

Offer, then accept the answer. Do not ask twice, and do not save a list the user did not agree to.

## Workflow

### Step 1: Save It

```
add_to_list(list_name, media_type, title, note)
```

`add_to_list` creates the list when it does not exist, so a new list needs no setup call. Use `create_list(name, description)` only when the user wants a named, described list to fill later.

The `note` field holds the reason an item earned its place. Fill it when the conversation gave you one, since the reason is what makes a list worth reopening.

### Step 2: Items Must Exist First

Lists point at library items. If a title is not in the library yet, `lookup_item` then `add_item`, then add it to the list in the same turn. Say the item was added in half a line and move on.

### Step 3: Read Before You Speak

```
get_list(name)      # one list, in order
get_list()          # every list, with counts
```

Never describe a list from conversation memory. Call `get_list` and report what came back. A list the user built weeks ago is the part you are most likely to get wrong.

### Step 4: Remove Cleanly

```
remove_from_list(list_name, title)
```

Removing takes the item off the list and leaves it in the library. Say so, so nobody worries they deleted something.

## Notes

- Lists cross media types by design. A list holding an album, two films, and a game is working as intended.
- Name lists the way the user talks. "Beach house" beats "Summer Media Queue".
- Sharing happens in the app. When someone wants to send a list to a friend, point them at the list in Achriom, where a private share link can be created.
- One list per idea. When a new grouping overlaps an old one, check `get_list()` first and offer to extend the list that already exists.

## Voice

Light and unfussy. The offer is one sentence, the confirmation is one line, and the note attached to each item carries whatever insight the conversation produced.
