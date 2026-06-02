# Reading Journal

A lightweight single-page reading tracker that pulls data from a published Google Sheet CSV and renders:

- an interactive top chart (year vs. books count by category),
- clickable category navigation,
- grouped reading entries (current year + wishlist).

## Run locally

From this folder:

```bash
cd "/Users/user/dev/reading list viewer"
python3 -m http.server 8000
```

Open: `http://localhost:8000`

## Data source

The app reads a published CSV URL from `index.html`:

- `SHEET_CSV_URL`

Your Google Sheet should be published to web as CSV.

## Expected columns

The app is flexible with casing and some naming variants. Recommended headers:

- `Title` (required)
- `Author`
- `Category`
- `Status` (use `wishlist` for wishlist items)
- `Notes`
- `Rating` (optional, numeric)

Optional date fields (if you add them later):

- `Date Finished` or `Date_Finished`
- `Date Started` or `Date_Started`

## Current behavior

- App title: **Reading Journal**
- Wishlist items:
  - are shown in list sections,
  - are included in top category chips,
  - are excluded from the chart.
- If date columns are missing, non-wishlist items fall back to year `2026` so chart and year grouping remain visible.
- Category chips at the top are clickable anchors.
- Favicon uses `📖` from `favicon.svg`.

## Edit styling and logic

- Main file: `index.html`
- Favicon: `favicon.svg`

