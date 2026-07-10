---
name: watched
description: Episode-level TV tracking. Log what you watched, find where you left off, and see what episode is next across your shows
argument-hint: "<show and episodes, or 'where was I'>"
allowed-tools:
  - mcp__plugin_achriom_achriom__mark_tv_watched
  - mcp__plugin_achriom_achriom__get_show_progress
  - mcp__plugin_achriom_achriom__get_by_status
  - mcp__plugin_achriom_achriom__lookup_item
  - mcp__plugin_achriom_achriom__add_item
---

# /watched: Keep the Watch State True

Episode-level tracking with the friction of a sentence, like a friend keeping score.

## Invocation

```
/watched two more episodes of Severance
/watched Andor through S2E5
/watched where was I on Silo?
/watched what should I catch up on
```

## Workflow

### Step 1: Log What They Said

"I watched X" or "caught up through S2E5" means exactly that:

```
mark_tv_watched(...)
```

Watching through an episode means everything up to it. Do not ask episode-by-episode questions; take the statement whole.

### Step 2: Answer "Where Was I"

```
get_show_progress(title)
```

Answer with the next unwatched episode by name and number, plus one line of where the story stands if the overview supports it. Never spoil beyond what they have seen.

### Step 3: The Catch-up Sweep

When they are returning after time away:

```
get_by_status(media_type="show", status="watching")
```

List their in-progress shows compactly, next episode each, then update whichever they name.

### Step 4: Unknown Show

If a named show is not in the library: `lookup_item`, then `add_item`, confirm in half a line, and continue the check-in in the same turn.

## Voice

Quick and companionable. Confirmations are one line. The user is telling you about their evening, not filing a report.
