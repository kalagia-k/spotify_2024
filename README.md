# Spotify Listening Dashboard (Power BI)

An interactive Power BI report that analyzes Spotify listening behavior:
Top artists/albums, time trends, device usage, and KPIs (skips & shuffle).

![Overview](images/overview.png)

## What’s included
- **Spotify_Dashboard.pbit** – template without data (recommended for reuse)
- **/images/** – preview images for this README

## Transformations (Power Query)
- Combine JSONs from folder → expand to columns
- Time fields: **Date**, **Year**, **Month Name**/**Month Abbrev**, **Day Name**, **Hour**
- Booleans: `skipped`, `shuffle`
- Readable labels for `reason_start` / `reason_end`
- Artist → **Genre** mapping (and optional multi-genre split for pies)

## Measures (DAX)
- **Total Listening Time** = `SUM(minutes_played)` or `SUM(msPlayed)/60000`
- **% Skipped**, **% Shuffle** (boolean ratios)
- **Most Listened Album** for selected artist
- **Top-N artists** logic (via calculated table or `TREATAS` measure)

## Main visuals
- **Top 15 Artists by Listening Time** (bar)
- **Genre breakdown for Top-N** (donut)
- **Listening time by Month** (col/line)
- **Device breakdown** (donut)
- Cards: **Most Listened Date**, **Most Listened Album**, **% Skipped**, **% Shuffle**