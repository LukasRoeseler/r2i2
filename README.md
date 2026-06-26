# R2I2 — Replication Research Issue Images

A browser-based tool for generating annual cover images for *Replication Research* (R²). Open `r2i2.html` in any modern browser — no installation, no account, no internet connection required after the page loads.

---

## Quick start

1. Open `r2i2.html` in your browser (Chrome or Firefox recommended).
2. The journal logo loads automatically in the center.
3. Set **Volume number** and **Year** in the sidebar.
4. Pick a **pattern** and **accent color** for this year's issue.
5. Click **↺ Regenerate** until you like the arrangement.
6. Choose an export resolution and click **⬇ Export PNG**.

That's it. The file is ready to upload to OJS.

---

## Sidebar reference

### Center image

The journal logo (`pageHeaderLogoImage_en_US.png`) is loaded automatically when the page opens. You can replace it with any image by clicking the upload zone or dragging a file onto it.

| Control | What it does |
|---|---|
| **Position** | 3×3 grid — click a cell to move the image to that corner, edge, or center of the cover |
| **Image size** | How wide the image is as a percentage of the cover width |
| **Padding from edge** | Gap between the image and the nearest edge (only matters when not centered) |
| **Image background** | Fills the area behind the image: transparent, white, black, or the current accent color |
| **Remove image** | Replaces the uploaded image with the drawn R² logo fallback |

### Volume & Year

Sets the label that appears on every cover, formatted as **Volume X | YYYY**.

| Control | What it does |
|---|---|
| **Volume number** | The issue number (e.g. `1`) |
| **Year** | The publication year (e.g. `2025`) |
| **Label position** | Where the label sits on the cover — bottom center is the default |
| **Label color** | Auto adjusts for contrast; or choose white, black, accent color, or a custom hex |

The label sits inside a semi-transparent pill so it stays legible over any pattern or background color.

### Pattern

23 patterns across two groups.

**Geometric patterns** tile the canvas with a repeated shape:

| Pattern | Character |
|---|---|
| Grid of R letterforms | The journal's R lettermark, scattered across the page |
| Halftone dots | Classic print halftone grid |
| Diagonal lines | Parallel stripes at an angle |
| Crosshatch | Two overlapping sets of diagonal lines |
| Triangles | Randomly rotated triangles, filled or outlined |
| Wave bands | Flowing horizontal sine waves |
| Hexagons | Honeycomb grid, filled or outlined |
| Concentric rings | Rings radiating from a shifting center |
| Diamonds | Rotated squares, filled or outlined |
| Zigzag stripes | Jagged horizontal bands |
| Grid squares | Rotated rectangles on a grid |
| Polka dots | Uniform dot field with size variation |
| Chevrons | Repeating V-shapes in horizontal bands |

**Recursive / fractal patterns** subdivide and repeat at multiple scales:

| Pattern | Character |
|---|---|
| Sierpiński triangles | Classic triangle fractal, tiled across the page |
| Cantor dust | Recursive bars that split and shrink |
| H-tree branches | Symmetric branching tree grown from the center |
| Nested boxes | Rectangles inside rectangles, slightly rotated |
| Recursive spirals | Paired spirals that spawn smaller spirals |
| Fractal tree | Organic-looking branching trees |
| Greek cross fractal | Cross shapes that sprout smaller crosses |
| Barnsley fern cells | Points scattered into a fern leaf silhouette |
| Penrose-like tiles | Quasi-symmetric five-fold tiling |
| Mondrian subdivisions | Recursive rectangular grid à la Mondrian |

**Density** controls how many elements fill the page (sparse → dense).  
**Randomness** controls how much variation there is in size, position, and rotation (uniform → wild).  
**↺ Regenerate** picks a new random arrangement while keeping all other settings the same.

### Color

| Control | What it does |
|---|---|
| **Accent color** | The main color used in the pattern and optionally the background and label. Pick from swatches or use the color picker for any hex value. |
| **Background** | White, black, the current accent color, or a fully custom color |
| **Pattern opacity** | How visible the pattern is — lower values let the background breathe through |

**Tip:** Each year's cover should use a different accent color. The pattern and color together are what make issues visually distinct on a shelf or in a TOC.

### Export / Resolution

Choose an export size before downloading. The canvas redraws at the new resolution immediately so you can check how the cover looks.

| Preset | Size | Use for |
|---|---|---|
| A4 print — 250 dpi | 2100 × 2970 px | Print-quality archival copy |
| A4 72 dpi | 1748 × 2480 px | Screen use, lighter file size |
| **OJS default** | **800 × 1200 px** | **Recommended for OJS upload** |
| OJS thumbnail | 500 × 700 px | OJS issue thumbnail |
| A4 150 dpi | 1240 × 1754 px | Mid-quality print |
| A4 300 dpi | 3508 × 4961 px | High-resolution print |

You can also enter a custom width and height and click **Apply custom size**.

Click **⬇ Export PNG** to download. The filename includes the resolution (e.g. `replication-research-cover-800x1200.png`).

---

## Uploading to OJS

1. Log in to the OJS editorial backend.
2. Go to **Issues** → edit the relevant issue → **Cover Image**.
3. Upload the exported PNG (800 × 1200 px recommended).
4. Save the issue.

OJS displays the cover on the issue archive page and in the table of contents.

---

## Year-to-year workflow

There is no saved state — settings reset when you reload the page. The suggested workflow for keeping covers consistent across years:

1. Note down the accent color hex value and pattern name for each year's cover (a simple spreadsheet works well).
2. For the new issue, pick a color and pattern that haven't been used before.
3. Click Regenerate a few times and screenshot or export candidates before settling on one.
4. Export at OJS default resolution and archive a copy at A4 300 dpi for print.

---

## Technical notes

- **Single file.** `r2i2.html` has no external dependencies beyond Google Fonts (loaded on first open). It can be hosted as a GitHub Pages site by placing the file in any repository with Pages enabled, or opened directly from your computer.
- **No data is sent anywhere.** Everything runs locally in the browser. Uploaded images never leave your machine.
- **CORS note.** The journal logo is fetched automatically from the OJS server. If your browser blocks this (e.g. when opening the file from a local path rather than a web server), the logo will fall back to a drawn version. Simply drag and drop the logo PNG onto the upload zone to restore it.
- **Browser support.** Chrome 90+, Firefox 88+, Edge 90+, Safari 15+. Internet Explorer is not supported.
