# Field Atlas — Kharif 2025

An interactive, map-first dashboard of the Kharif-2025 field study: water level, water
meter, methane, and the endline "Farm Info", all tied to each farm on a real map
(satellite / topographic / political basemaps).

It is a **static site** — one `index.html` file with the data baked in. No server, no
database. You can double-click `index.html` to run it locally, or host it online for free
(below).

---

## Put it online with Vercel (free — about 5 minutes)

You already use Vercel for the pipe tool, so this is the same flow.

### Step 1 — Put these files on GitHub
1. Go to **https://github.com** and sign in.
2. Click the **+** (top-right) → **New repository**.
3. Name it e.g. `field-atlas` → keep it **Public** (or Private, both work) → **Create repository**.
4. On the new repo page click **“uploading an existing file”**.
5. Drag in the **contents of this folder** — `index.html` and `README.md` — and click **Commit changes**.
   *(If you were given a `.zip`, unzip it first, then upload the files inside.)*

### Step 2 — Deploy on Vercel
1. Go to **https://vercel.com** and sign in **with GitHub**.
2. Click **Add New… → Project**.
3. Find your `field-atlas` repo in the list → **Import**.
4. Leave every setting at its default (Framework Preset = **Other**; no build command needed —
   it's a plain static site).
5. Click **Deploy**. Wait ~30 seconds.
6. You get a live link like `https://field-atlas.vercel.app`. That's your tool, online. Share it.

### Step 3 — Updating it later
Whenever the tool changes, replace `index.html` in the GitHub repo (upload the new file,
Commit). Vercel redeploys automatically within a minute — same link.

### Optional — a custom web address
In Vercel: your project → **Settings → Domains** → add a domain you own (e.g.
`atlas.yourlab.org`). Follow the DNS instructions it shows.

---

## Run it locally (no internet host needed)
Double-click `index.html`. It opens in your browser. (It needs internet **while open** so the
satellite/street map imagery can load — that part streams from map servers.)

---

## What's inside
- `index.html` — the entire tool (HTML + CSS + JavaScript + the data, all in one file).
- Data is the joined Kharif-2025 bundle: ~441 monitored farms across 39 villages.

## Notes / next steps
- Uses the **revised** `kharif25_all_pipes_readings.xlsx` (QC'd water) and
  `kharif25_meter_for_tool.xlsx` (per-farm daily m³/acre).
- **Crop-calendar phases** are the real 5 stages — Sowing · Transplant · Vegetative ·
  Flowering · Grain-fill — from each farm's dates in the meter `master` tab.
- Study groups (AWD control/treatment/training) are intentionally ignored — all farms treated
  as one.
- **Methane** covers only the sampled fields (no season time-series exists for it).
- Field **photos** (Google-Drive folder) and **remote-sensing layers** (like the Earth Engine
  app) are not wired in yet — planned next.
