# Montfort · Qal'at Qurein — reconstruction site

Single static file, no build step. Works on GitHub Pages or any static host.

## Deploy
1. Put `index.html` in a repo (root or `/docs`).
2. Enable GitHub Pages for that folder.
3. Open the page. It fetches, at load time:
   - elevation: Mapzen Terrain Tiles via AWS Open Data (zoom 15, four tiles)
   - imagery: Esri World Imagery (zoom 18, about 110 tiles)

Both services need no key. Previews inside chat tools or sandboxed iframes usually block these fetches; the page then falls back to plan derived terrain and says so on screen.

## Calibrate once
The castle sits at 33.0447°N 35.2261°E with its long axis on bearing 67° (keep toward ENE), read from the north arrow on the book's chamber plan. Expect a few tens of metres of offset.

1. Click **Calibrate position**.
2. Switch to the *today* state and zoom in. The ruin walls show clearly in the imagery.
3. Move the bearing and shift sliders until the keep and the long range sit on the visible wall lines. Use *Raise / lower* if the massing floats or sinks (the 30 m DEM smooths the ridge top).
4. Place the mill on the valley building the same way.
5. Copy the values from the text box into `CFG` at the top of the script. Done.

## Known limits
- Terrain source resolution is about 30 m. Gorge and slopes are real; the narrow ridge top is smoothed. Finer data (Survey of Israel DTM, or the MCP's own scans) can replace `loadTerrain()` later.
- Rock cut moats are carved into the DEM from the published dimensions (inner 20 × 11 m, outer 10 × 13 m) because 30 m data cannot show them.
- Two states only: c. 1240 and today. The Gothic Hall found in 2018 is not modelled yet (no published dimensions).
- Attribution to Esri and Mapzen/AWS must stay visible; both licences require it.
