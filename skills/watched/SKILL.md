---
name: watched
description: Log what you watched, with dates. Episode-level TV tracking, rewatches of films and shows, where you left off, and what episode is next
argument-hint: "<show and episodes, or 'where was I'>"
allowed-tools:
  - mcp__plugin_achriom_achriom__mark_tv_watched
  - mcp__plugin_achriom_achriom__get_show_progress
  - mcp__plugin_achriom_achriom__get_by_status
  - mcp__plugin_achriom_achriom__lookup_item
  - mcp__plugin_achriom_achriom__add_item
  - mcp__plugin_achriom_achriom__log_event
  - mcp__plugin_achriom_achriom__set_dates
  - mcp__plugin_achriom_achriom__delete_event
  - mcp__plugin_achriom_achriom__update_status
---

# /watched: Keep the Watch State True

Episode-level tracking with the friction of a sentence, like a friend keeping score.

## Invocation

```
/watched two more episodes of Severance
/watched Andor through S2E5
/watched where was I on Silo?
/watched what should I catch up on
/watched Heat again last night
/watched finished The Wire back in 2019
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

### Step 4: Films, Rewatches, and Dates

A film they finished for the first time is a status: `update_status(media_type="movie", title, status="watched")`, plus `set_dates(..., finished_at=...)` when they said when.

A rewatch ("watched Heat again", "rewatched all of Twin Peaks") is an event, so it shows in their history without erasing the first time:

```
log_event(media_type, title, event_type="rewatched", event_date="2026-09-25")
```

When they only know roughly when ("back in 2019"), pass the year alone; it is kept as a year. To fix a date, `set_dates`; to take back a log, `delete_event` (with more than one event on the item it lists them with ids first).

### Step 5: Unknown Show

If a named show is not in the library: `lookup_item`, then `add_item`, confirm in half a line, and continue the check-in in the same turn.

## Voice

Quick and companionable. Confirmations are one line. The user is telling you about their evening, not filing a report.
