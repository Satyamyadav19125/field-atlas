# Field Atlas — Kharif 2025 (Level 3)

An interactive, map-first dashboard of the Kharif-2025 field study: water level, water
meter, methane, farm info and **field photos**, all tied to each farm on a real map
(satellite / topographic / streets, dark & light). Static site — no server, no database.

Live: https://field-atlas-ashy.vercel.app/

## What's in this folder (push ALL of it to GitHub)
- `index.html` — the whole tool
- `photos/` — the field-photo thumbnails (referenced by the tool)
- `apple-touch-icon.png`, `icon.svg`, `icon-192.png`, `icon-512.png`, `favicon-32.png` — the app icon (home-screen icon on iOS)
- `README.md`

> Since Level 3 adds photos and an icon, you now upload the **whole folder**, not just
> `index.html`. On github.com open your repo → **Add file → Upload files** → drag the
> **contents of this folder** in (or drag the `field-atlas-repo` folder) → **Commit**.
> Vercel redeploys automatically. (After the first time, to update the tool you only
> replace `index.html` again.)

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
map layers show. Everyone else sees the finished product.

## Notes
- Data is fixed for Kharif 2025 (from the KML + Excel). To change the numbers we re-import
  and ship a new Level.
- Photos: 286 of the 441 farms have field photos (the ones the team shared).
- Crop stages: Nursery · Transplanting · Vegetative · Reproductive · Maturity (stages with
  no readings are hidden).
