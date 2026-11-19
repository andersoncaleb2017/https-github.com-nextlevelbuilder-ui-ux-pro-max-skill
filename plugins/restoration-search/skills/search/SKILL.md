---
name: search
description: Look up The Restoration Hotel (therestorationhotel.com, Charleston SC, plus its Asheville NC sister property) on the web and answer questions about it with sources. Use when the user asks about the hotel's details, rooms, amenities, policies, rates, reviews, press, or what the web currently says about it.
---

# Search: The Restoration Hotel

Answer questions about The Restoration Hotel from live web sources, not memory.

## Known facts (check before quoting; they may change)

- Official site: https://therestorationhotel.com (machine-readable summary at /llms.txt)
- Flagship: 75 Wentworth St, Charleston, SC 29401, in the Historic District off King Street
- 54 suites, 750–2,300 sq ft; opened January 2016 after a $27M renovation
- Amenities: The Watch restaurant, rooftop bar, coffee shop, library, boutique shop, guests-only rooftop pool (The Indigo)
- Check-in 4:00 PM, check-out 11:00 AM
- Sister property: The Restoration Hotel Asheville, NC (opened 2023)

## Steps

1. Restate the question in one line and decide which property it is about (Charleston by default).
2. Run WebSearch. Start with the official domain
   (`allowed_domains: ["therestorationhotel.com"]`), then search broadly
   (booking sites, Charleston CVB, press, review sites).
3. If a result does not settle the question, fetch the page and read it.
4. Compare sources. If they disagree (pet policy is a known example), say so
   and treat the official site as the tiebreaker. Never pick one quietly.
5. Never invent prices or availability. Rates depend on dates, so give a
   current snapshot with its source and date, or point to the booking page.

## Output

- A short answer first, then bullet details.
- Flag anything uncertain or contradictory.
- End with a `Sources:` list of markdown links to every page you used.
