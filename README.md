# Field Atlas — Kharif 2025 (Level 4)

An interactive, map-first dashboard of the Kharif-2025 field study: water level, water
meter, methane, farm info and **field photos**, all tied to each farm on a real map
(satellite / topographic / streets, dark & light). Static site — no server, no database.

Live: https://field-atlas-ashy.vercel.app/

## What's new in Level 4
- **Mobile fixed** — the map sits on top and the whole panel scrolls; everything is
  reachable on a phone. Search + village now share one row; KPIs reflow on small screens.
- **Overview is now a full study report** — season line, week-by-week and per-crop-stage
  charts for both water level and water use across all farms, plus a lab soil-composition
  summary. Tapping any field still opens its complete per-farm dossier.
- **Water level axis is 0–300 mm** (the AWD pipe range) with the soil line at 150 — no more
  −50.
- **Water-use (meter) charts auto-scale to each field**, so the bars are never dwarfed by a
  fixed axis. Daily, weekly and per-stage views for every metered field.
- **Monitoring-point count fixed** — read from the water-pipe readings, so fields with data
  no longer show "0 pipes".
- **Selected polygons keep their colour** (highlighted with an outline) instead of going dark.
- **Water-source facts** (tubewells, pump HP, borewell depth, water table, delivery-pipe
  width) and **lab soil composition** (sand / silt / clay %) added to the water, meter and
  farm-info cards.
- **Monitoring points & tubewells are hidden by default** and only revealed from the admin
  **Settings → Map layers** toggles.

## What's in this folder (push ALL of it to GitHub)
- `index.html` — the whole tool
- `photos/` — the field-photo thumbnails (referenced by the tool)
- `apple-touch-icon.png`, `icon.svg`, `icon-192.png`, `icon-512.png`, `favicon-32.png` — the app icon (home-screen icon on iOS)
- `README.md`

> Upload the **whole folder** (it includes the photos and icon). On github.com open your
> repo → **Add file → Upload files** → drag the **contents of this folder** in → **Commit**.
> Vercel redeploys automatically. (After the first time, to update the tool you only replace
> `index.html`.)

## Put it online with Vercel (first time)
1. github.com → **New repository** (Public) → Create.
2. **Upload files** → drag everything in this folder → **Commit**.
3. vercel.com → sign in with GitHub → **Add New → Project** → Import the repo → **Deploy**.
4. You get a link like `https://field-atlas.vercel.app`.

## Run it locally
Open `index.html` in a browser (keep it inside this folder so the `photos/` load).
Needs internet for the map imagery.

## Admin
The 🔒 button (password **`dv2025`**) unlocks a Settings tab: theme, base map, and which
map layers show — including the monitoring points and tubewells, which are off for viewers.

## Notes
- Data is fixed for Kharif 2025 (from the KML + Excel). To change the numbers we re-import
  and ship a new Level.
- Photos: 177 farms have a field photo (one recent shot each, from the team's uploads).
- Crop stages: Nursery · Transplanting · Vegetative · Reproductive · Maturity (stages with
  no readings are hidden).
