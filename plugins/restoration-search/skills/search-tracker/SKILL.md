---
name: search-tracker
description: Track where therestorationhotel.com ranks in web search for a set of keywords over time, saving each run to a CSV log and reporting changes since the last run. Use when the user wants to check, record or compare the hotel's search rankings, or add or remove tracked keywords.
---

# Search Tracker: therestorationhotel.com

Record the hotel's search positions on each run and report what changed.

## Files (in the current working directory)

- `search-tracker/keywords.txt`: one keyword per line. Create it with the
  defaults below if it does not exist.
- `search-tracker/rankings.csv`: append-only log with the header
  `date,keyword,position,ranking_url,top_result_url,notes`

Default keywords:

```
the restoration hotel
the restoration charleston
boutique hotel charleston sc
luxury hotel charleston historic district
hotels on king street charleston
charleston hotel rooftop pool
suite hotel charleston
the restoration hotel asheville
boutique hotel asheville nc
```

## Steps

1. Read `keywords.txt`. If the user asked to add or remove keywords, update
   the file first and show the new list.
2. For each keyword, run WebSearch (standard mode) once.
3. Position = rank (1-based) of the first result whose URL is on
   `therestorationhotel.com`. If none appears, record `position` as `not found`.
   Also record the top result's URL. In `notes`, add whether an OTA
   (Booking, Expedia, etc.) or a listing page ranks above the official site.
4. Append one row per keyword to `rankings.csv` with today's date (YYYY-MM-DD).
   Never edit or delete earlier rows.
5. Compare with the most recent earlier date in the CSV.

## Report

A table: `Keyword | Today | Last run | Change | Ranking URL`, with ▲/▼ for
moves, "new" for first-time keywords, and "lost" when it drops out.
Then 2–3 sentences on the biggest movements and one suggested next step
(for example, run the `search-fixer` skill on a page that lost ground).

## Caveats to state

Web search positions are an approximation: results vary by location,
personalization and time, and the search tool may return fewer results than
a full Google page. Compare runs from the same tool over time instead of
treating any one position as exact.
