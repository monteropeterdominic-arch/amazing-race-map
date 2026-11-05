# 🏁 USM Amazing Race Map

Interactive web map (Mapbox GL JS) of the 10 Amazing Race stations at the University of Southern Mindanao, Kabacan.

**Live:** https://monteropeterdominic-arch.github.io/amazing-race-map/
**Edit mode:** https://monteropeterdominic-arch.github.io/amazing-race-map/?edit

| # | Station |
|---|---------|
| 1 | CTI Canteen (start) |
| 2 | ICT Building |
| 3 | Library |
| 4 | CEIT Canteen |
| 5 | Playground near CEIT Canteen |
| 6 | CEIT Court |
| 7 | CEIT Lobby |
| 8 | CTI Building (in front of CEIT) |
| 9 | Guard House (FMD Building) |
| 10 | DOST Laboratory near CEIT (finish) |

## Features
- Satellite basemap, numbered station markers, dashed route 1 → 10 with direction arrows
- Live GPS location (blue dot) + distance and direction to the next station
- Tap ✔ to mark a station found; progress saved on the phone
- Edit mode: drag markers or drop a station at your current GPS position, then download `stations.geojson`

## ⚠️ Fix the station positions before the race
The starting coordinates are **approximate** (laid out from the hand-drawn sketch). Correct them with either method, then replace `stations.geojson` in this repo.

### Option A — on the phone, walking the course (most accurate)
1. Open the `?edit` link, allow location.
2. At each station tap **📍 Here** on that row.
3. Tap **⬇ Download stations.geojson** and upload it to the repo (Add file → Upload files, overwrite).

### Option B — QGIS
1. Layer → Add Vector Layer → `stations.geojson`.
2. Add a satellite basemap (XYZ Tiles → Google Satellite / Esri World Imagery).
3. Toggle Editing → Vertex tool, drag each point onto the right building. Edit `name`/`clue` in the attribute table if you like.
4. Save edits, then right-click → Export → Save Features As… → GeoJSON, CRS **EPSG:4326**, file name `stations.geojson`.
5. Upload to the repo, overwriting the old file.

## Deploy (GitHub Pages)
Settings → Pages → Source: *Deploy from a branch* → Branch `main`, folder `/ (root)` → Save. The link is live in ~1 minute.

## Mapbox token
The public `pk.` token is in `index.html`. In your Mapbox account → Tokens, add a URL restriction for
`https://monteropeterdominic-arch.github.io/*` so nobody else can use it.
