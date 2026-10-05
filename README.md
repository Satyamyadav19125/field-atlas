# Field Atlas — Kharif 2025 (Level 9)

## What's new in Level 9
- **Photos are back — pipe *and* field.** Both the tape-meter-inside-the-pipe shot and the
  field-from-above shot show on a farm's card (labelled), restored from the survey.
- **Chart wording cleaned up** — the dashed line is now **"Ground level"** (only next to the
  line, not repeated in the subtitle); water charts read *Average Daily Water Level*,
  *Weekly Average Water Level*, *Average Water Level by Crop Stage*; the meter is now called
  **irrigation water** (not "water use", which could be read as including rain) and its
  charts say *Average … Irrigation Water …*; rankings say **per farm**.
- **Dodgy readings are filtered out.** A field needs at least 5 readings that fall inside its
  season to get a water figure; farms with one stray reading (the old "0 mm" entries) or no
  transplant date are now left out of the averages, rankings and map colour, and their card
  explains why instead of showing an empty chart.
- **No more empty Zinc bar** when a field used no zinc.
- **Water-source card** notes when pump/borewell figures are for the *main* tubewell (fields
  with more than one).

### Photos from Google Drive (optional, live)
By default the tool uses the photos in the `photos/` folder. To serve them **live from your
Google Drive** instead — so adding a photo there and clicking *Refresh* shows it, with no
re-upload:
1. Put the survey photos in one Google Drive folder → **Share → "Anyone with the link".**
2. Make a Google **API key** with the **Drive API** enabled (Google Cloud Console →
   *APIs & Services*), and restrict it to your site's web address.
3. Open `index.html`, find the block near the bottom that starts
   `GOOGLE DRIVE PHOTOS (optional)`, and paste your **folder id** (the long code in the
   folder's link) and the **API key** between the quotes. Save and re-publish.
The tool matches each farm's survey photo by its filename, so you do **not** need to rename
anything. In the app, **🔒 admin → Settings → Photos → Refresh** re-pulls from Drive after
you add new ones.

### Publish to GitHub in one click
Run **`publish-to-github.ps1`** (right-click → *Run with PowerShell*). It uploads this whole
folder — including photos — to your GitHub repo and makes the repo match this folder exactly
(old/stray files are removed). The first run asks for your repo URL once. Vercel then
redeploys on its own.

## What's new in Level 8
- **Every farm is now on the map.** Boundaries were re-synced from the updated
  `Digital Village 2023-25 - Farms.kml` (421 polygons refreshed, the last orphan point —
  Satnam Singh / 10450 — now has its real shape). 19 farms that have data but no boundary in
  the KML are placed at their village and clearly marked **"approximate"** (dashed marker +
  a note on the card), so nothing is hidden.
- **Resize the two panes.** Drag the bar between the map and the data panel to make either
  bigger (double-click it to reset). On a phone the bar sits under the map and resizes its
  height. Your size is remembered.
- **"Go to my location" button** (📍) and a **"fit to the study area" button** (⌂) on the map.
  Location needs the live `https` site (browsers block it on a local file).
- **Better fit on phones & tablets** — the stacked one-column layout now kicks in up to
  1024px wide, so large phones and tablets no longer get the cramped side-by-side view.
- **"How this field compares"** — each water / water-use card now shows whether the field is
  above, below, or about the study average.
- (Only `index.html` changed — `photos/` and icons are the same as before.)

## What's new in Level 7
- **Pie percentages now total exactly 100%.** The soil-composition slices were each rounded on
  their own, so they could read 68 + 21 + 12 = 101. They're now allocated with the
  largest-remainder method, so the labels always sum to 100. (Only `index.html` changed.)

An interactive, map-first dashboard of the Kharif-2025 field study: water level, water
meter, methane, farm info and **field photos**, all tied to each farm on a real map
(satellite / topographic / streets, dark & light). Static site — no server, no database.

Live: https://field-atlas-ashy.vercel.app/

## Updating
This update changes **only `index.html`**. The `photos/` folder and the app icons are
unchanged, so you don't need to re-upload them. On GitHub: **Add file → Upload files → drop in
the new `index.html`** → Commit. Vercel redeploys automatically.

## What's new in Level 6
- **Farmer names everywhere** — pulled from the updated survey (436 of 441 farms). Search,
  popups, farm cards and every ranking now show the farmer, not a plot number.
- **Missing field boundaries added** — the stray "points with no polygon" now draw their real
  KML shapes (Gurpreet Singh / Harpal Singh / plot 4064). One field (Satnam Singh, 10450) has
  no boundary in any KML yet, so it stays a marker until one is provided.
- **Charts polished** — every chart title is centred; a y-axis title (mm / m³/acre / kg/acre)
  now sits next to the axis; subtitles report the sample size as **n=**; gridlines are even;
  the season/weekly axes fit each field (no empty stretch to day 150); the study lines drop
  the noisy end-of-season tail where only a few farms still report.
- **Nursery removed from water level** — you can't read a pipe in the seedbed, so the water
  stages are now Transplanting → Maturity. (The meter keeps its pre-transplant land-prep water.)
- **Soil composition is a pie** ("Soil composition · Laboratory test") since sand + silt + clay
  make 100%.
- **Rankings split** into "highest" and "lowest" cards, whole numbers, uniform farmer names.
- **Tidier text** — tenure shows just "Owned / Rented / Leased"; overview photos removed (the
  top-down field shot lives on the Farm Info card only, where a photo exists).

## What's new in Level 5
- **Mobile fit fixed properly** — on a phone the page now scrolls as one document: the map
  is the hero at the top (44% of the screen), everything else flows below it. The map now
  redraws itself when the layout changes (so no more half-loaded satellite tiles), and the
  villages key shrinks so it no longer covers the map.
- **Map layers live on the map again** — Monitoring points and Tubewells are back in the
  map's own layer menu (the ▧ button, top-right of the map), off by default so the map stays
  clean. **Settings → Map layers** now decides whether each one even *appears* in that menu:
  set it to **Hidden** and it's dropped from the map's layer menu entirely.

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
