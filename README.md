# HexGlobe

An interactive hex-grid globe for building and editing worlds. Terrain is generated on a geodesic sphere, shown as a rotatable 3D globe and as a synchronised 2D equirectangular map, and can be painted by hand.

## Running the demo

Open `index.html` in a modern browser. It is a single self-contained file: the Earth heightmap is embedded, and the libraries load from CDNs (React 18, Babel Standalone, Three.js 0.160.0, Tailwind CSS). An internet connection is needed for the first load.

To publish on GitHub Pages, upload `index.html` to the repository, then enable Pages under Settings → Pages.

## Features

- **Hex grid:** vertex-centred hexagons on an icosahedral sphere. Detail level sets the resolution (10 × 4ⁿ + 2 hexes; the default level 4 gives 2,562).
- **World types:**
  - *Earth* (default): the embedded heightmap.
  - *Procedural*: randomly generated terrain.
  - *Blank Canvas*: flat plains to paint on.
  - *Upload*: your own elevation heightmap, with an optional ocean mask and a toggle to use or ignore it.
- **Painting:** brush (adjustable size and value), line, and flood fill, on both the 3D globe and the 2D map. Undo keeps up to 20 steps.
- **Views and controls:** 3D, 2D, or both. Drag to rotate, scroll or use the zoom slider to zoom, arrow keys to rotate, and a recenter button.
- **Provinces:** 20 provinces are generated over the grid.

## Ocean masks

When using *Upload*, a greyscale ocean mask can be supplied: white pixels are ocean (elevation 0.0), and any other colour is land (elevation 0.1 to 1.0). Turn the mask off to compare against the elevation threshold.

## Files

- `index.html`: the complete application.
- `HexGlobeFramework_v2.jsx`: the same application source, for editing. Rebuild `index.html` from it after changes.
- `GRAY_LR_SR.jpg`: the Earth heightmap embedded in `index.html`. It is not needed to run the demo.

## Credits

- **Earth heightmap (`GRAY_LR_SR.jpg`):** Natural Earth, shaded relief raster (GRAY_LR_SR), https://www.naturalearthdata.com/downloads/. Natural Earth map data is in the public domain.
- **Code:** written with Claude (Anthropic), Claude Haiku 5.5, October 2026.
