---
name: games-analysis
description: Game analysis methodology. Use when exploring design, systems, developer style, platform history, or what makes a game hold up. Triggers on questions about mechanics, franchises, playtime, or why a game landed.
---

# Games Analysis

## When to Activate

- Discussing design, mechanics, or how a game plays
- Analyzing a developer or publisher's body of work
- Placing a game inside a franchise or a series arc
- Comparing games across platforms, generations, or genres
- Weighing what to play next against how long things take
- Any close reading of what makes a game work

## Analysis Approach

### 1. Gather Game Details
```
get_details(media_type="game", title="...")
```
Returns the developer, publisher, release date, platforms, genres, game modes, franchise, themes, mood, time to beat, critic score, and the user's own play status, platform, format, rating, and notes.

### 2. Find Related Games
```
search(media_type="game", query="developer, genre, platform, or theme")
```
Search matches on title, developer, publisher, summary, genres, platforms, and themes, so a studio name or a platform name both work as queries.

### 3. Video Content
Retrospectives, design breakdowns, soundtracks, speedruns:
```
search_youtube(query="game title design retrospective")
search_youtube(query="game title soundtrack")
```

### 4. Research Context
Use whatever web search tool the session has available:
```
tavily-search(query="game title development history postmortem")
```

## Discussion Patterns

**Systems and mechanics.** Describe the loop the player actually repeats, and say what the game asks of them while they repeat it.

**Developer identity.** Place the game in the studio's run of work, and say whether it extends the house style or breaks from it.

**Franchise position.** The `franchises` field tells you which family a game belongs to, which lets you ask what this particular entry was trying to fix, extend, or apologize for.

**Platform and era.** Hardware shapes design. A game built for a handheld, a living-room console, or a mouse and keyboard carries that origin in its pacing and its controls.

**Length and commitment.** `time_to_beat` gives the normal completion time in hours. A 12-hour game and a 90-hour game make different claims on a person's year, and that belongs in any recommendation.

**Mode.** The `game_modes` field separates single-player craft from multiplayer or co-op design. Say which one the analysis is about.

**Critic score against their rating.** `total_rating` is the aggregate out of 100. Where the user's own stars diverge from it, that gap is usually the interesting part of the conversation.

## Era Classification

- **Cartridge era (pre-1995):** fixed hardware budgets, arcade inheritance, score and mastery
- **3D transition (1995-2005):** cameras, controls, and level design being invented in public
- **HD and online (2006-2013):** patching, achievements, matchmaking, the cinematic turn
- **Open systems (2013-2020):** persistent worlds, systemic design, games as ongoing services
- **Current (2020+):** cross-platform play, day-one subscription release, revivals and remakes at scale

## Proactive Features

- **Read the play status honestly.** Games use unplayed, playing, played, saved, on hold, and abandoned. On hold and abandoned carry real information about the collection.
- **Surface the franchise thread.** When a franchise appears more than once, trace how the user's ratings move across entries.
- **Use time to beat in queue advice.** Match the recommendation to the time the user has.
- **Note the platform they own it on.** `platform` and `format` describe their copy, so a backlog suggestion should point at hardware they can reach.
- **Connect across media.** Games share adaptations, composers, and source material with the rest of the library.
- **Embed the soundtrack or a design video** rather than describing it.

## Attribution

Games metadata is powered by IGDB.com. Credit it when you present game metadata at length.
