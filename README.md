# CityRT Client Architecture and Systems

Extracted client bundle and architectural analysis of [CityRT](https://cityrt.com/en/), a browser-based, progressive web application (PWA) real-time city-building simulation game.

Preserved in the 0xleetv studio arsenal for studying lightweight simulation loops, canvas rendering, touch gestures, and municipal simulation state.

---

## 1. What is CityRT?
CityRT is a modern, zero-install web city builder where players construct roads, zone residential/commercial/industrial districts, manage municipal budgets, provide public utilities (schools, hospitals, fire stations, power grids, water networks), and run multiplayer town rooms.

---

## 2. Key Architecture and Component Breakdown

### Canvas Simulation Engine (`sketch-BVFKUE40.js`)
* Lightweight 32 KB canvas rendering loop.
* Fast isometric/grid tile drawing without heavy 3D engine overhead (pure 2D canvas context with layered alpha blending).
* Viewport culling and tick-rate management to ensure smooth performance across low-end mobile devices and desktop browsers.

### City Registry and Building Systems (`registry-DSgAPuQj.js`)
* Modular building registry detailing properties, costs, footprint matrices, power/water consumption, and municipal influence radiuses.
* Zoning mechanics: handles dynamic growth and occupancy simulation for residential, commercial, and industrial zones.

### Visual Themes and Skins (`_skins-CisHijTP.js`, `styles-Dxaoz1hf.js`)
* Multiple procedural colorways and visual aesthetic skins (Classic, Warm, High Contrast, Dark Mode).
* CSS architecture: `shell-CgIFjJ9M.css`, `main-B3WYD0Ra.css`, and `social-C48jZP6a.css`.

### Mobile Touch and Device Handling (`touch-KiUgAa9o.js`, `device-Cy-W0Lrf.js`)
* Full touch gestures: pinch-to-zoom, pan, drag-to-place, and multi-touch controls optimized for mobile browsers and PWA standalone mode.
* Dynamic viewport sizing and DPI scaling.

### Pass and Economy UI (`pass-Ch_fMtX-.js`, `passui-CStgJ0nC.js`)
* Anti-Bot Pass and room access authorization patterns.
* Lightweight transaction and receipt verification interface.

### Internationalization Engine (`i18n-DnqQ8hVZ.js`, `langurl-DaAJohq8.js`, `langpick-DoZ1pIOG.js`)
* Multilingual support across 11 languages (English, Russian, Ukrainian, Spanish, German, Simplified Chinese, Korean, Brazilian Portuguese, French, Italian, Polish).

---

## 3. How to Use and Pick from This Library
* **Lightweight Game Loops**: Extract the canvas grid renderer and viewport controller for 2D/isometric web games.
* **Touch Gesture Controls**: Adapt `touch-KiUgAa9o.js` for custom mobile gestures, pinch-zoom canvases, and interactive dashboards.
* **Simulation State Machines**: Study the municipal budget and zone satisfaction algorithms for resource-management interfaces.
