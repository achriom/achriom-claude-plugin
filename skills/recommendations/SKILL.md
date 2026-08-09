---
name: recommendations
description: Cross-media recommendation methodology. Use when suggesting what to read, watch, listen to, or play next. Considers mood, themes, and patterns across all seven media types. Triggers on "what should I..." or "recommend" questions.
---

# Recommendations

## When to Activate

- User asks what to read/watch/listen to next
- Looking for something similar to an item they loved
- Seeking a specific mood or vibe
- Want to explore a theme across media types
- "I'm in the mood for..."

## Recommendation Philosophy

**Mine their collection first.** They already own things they haven't explored. Surface those before suggesting new acquisitions.

**Cross-media connections.** If they loved a book's themes, find the film or album that shares that spirit.

**Respect their taste.** Their ratings and notes tell you what resonates. Use that signal.

## Recommendation Process

### 1. Understand the Request
What are they really asking for? Mood? Theme? Similar to something specific?

### 2. Check Their Collection
```
get_stats()  # Overall shape
get_by_rating(media_type, min_rating=4)  # What they love
search(media_type, query="relevant theme")
get_timeline(media_type)  # Recent engagement
```

### 3. Find Unread/Unwatched Gems
Search for items with matching themes the user has not started. The status word varies by type: `unread` for books, `unwatched` for movies, shows, and anime, `unheard` for albums, `unplayed` for games. Podcasts use `want_to_listen` through `get_by_status`.
```
search(media_type="book", query="theme", filter="unread")
search(media_type="game", query="theme", filter="unplayed")
get_by_status(media_type="podcast", status="want_to_listen")
```
For games, weigh the completion time from `get_details`. A recommendation that costs 60 hours needs a better reason than one that costs 8.

### 4. Cross-Media Bridge
If they loved a book, search films:
```
search(media_type="movie", query="theme from book")
```
Make explicit connections: "The melancholy in [book] shows up visually in [film]..."

### 5. Research New Suggestions
If nothing in collection fits, research:
```
tavily-search(query="books similar to [title] theme")
```

## Recommendation Patterns

**The unread shelf:** "You have [book] sitting unread - given how much you loved [similar book], this might be the moment."

**The mood match:** "You rated [dark album] highly. [Other album] has that same weight."

**The thematic thread:** "This theme of isolation runs through your highest-rated items. Here's where else it appears..."

**The cross-pollination:** "The director of [film] was influenced by [author] - you have both in your library."

## Always Include

- **Why** this recommendation fits (don't just list titles)
- **Something to sample** - a track preview, a YouTube clip, a book passage
- **The connection** to what they already love
