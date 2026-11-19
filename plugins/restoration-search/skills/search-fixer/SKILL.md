---
name: search-fixer
description: Find and fix problems with how therestorationhotel.com appears in search results, including titles, meta descriptions, indexability, structured data (Hotel schema), local/NAP consistency and inaccurate third-party listings. Use when the user asks why the hotel ranks poorly, wants SEO fixes for the site, or wants wrong information about the hotel corrected.
---

# Search Fixer: therestorationhotel.com

Diagnose search-visibility problems for The Restoration Hotel and turn each
one into a concrete fix. Only report problems you have evidence for.

## 1. Gather evidence

Fetch and inspect these pages (add others the user names):

- https://therestorationhotel.com/ (home)
- Rooms/suites, dining (The Watch), amenities, Asheville and contact pages, found by following links from home
- https://therestorationhotel.com/robots.txt and /sitemap.xml (or the sitemap that robots.txt lists)
- https://therestorationhotel.com/llms.txt

Then search the web for `"The Restoration" Charleston hotel` and
`site:therestorationhotel.com` to see what results and snippets show.

## 2. Check each page

| Area | What to check |
|---|---|
| Indexability | HTTP 200, no stray `noindex`, canonical points to itself, page is in the sitemap |
| Title | Unique, under ~60 chars, includes "The Restoration" plus "Charleston" (or "Asheville") and the page topic |
| Meta description | Present, under ~155 chars, specific (suites, rooftop pool, Historic District) |
| Headings | Exactly one H1 that matches the page's purpose |
| Structured data | `Hotel`/`LodgingBusiness` JSON-LD with name, address, geo, telephone, checkinTime/checkoutTime, amenityFeature, petsAllowed; `Restaurant` for The Watch |
| NAP consistency | Name, address (75 Wentworth St, Charleston, SC 29401) and phone are identical on the site, Google Business Profile listing, and major OTAs |
| Images | Descriptive alt text on room/amenity photos |
| Links | No broken internal links; Charleston and Asheville pages link to each other |

## 3. Check third-party accuracy

Compare facts across booking sites (Booking.com, Expedia, Hotels.com, Trip.com,
Kayak), Charleston CVB and press pages. Pets policy is a known conflict.
List every mismatch with the source URL and the correct value from the
official site.

## 4. Report

Start with a ranked **Top 5 fixes** (impact first, then effort). Then a full
table: `Issue | Evidence (URL + what you saw) | Fix | Owner (dev / content / listings) | Effort`.

For each structured-data or title fix, include the ready-to-paste
replacement (JSON-LD block or exact title/description text).

Do not change anything outside the user's own files. If the user's site
code is in the workspace, propose edits and apply them only after the user
approves. Third-party listings are fixed by the hotel through each
platform's owner portal, so list those as instructions, not actions.
