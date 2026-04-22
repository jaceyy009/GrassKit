# GrassKit — Minecraft Biome Colormap Tinter
**By Jace Castillo**

A desktop tool for tinting Minecraft textures using biome colormap data from the Bedrock sample resource pack.

---

## Features
- All 58+ Bedrock biomes with real temp/downfall values
- Grass and foliage colormap support
- Tint mask (white = tint, black = keep original)
- **Grass Side Mode** — upload overlay + dirt base separately, GrassKit composites them
- Manual temperature/humidity sliders
- Expand previews to fullscreen
- Export as PNG
- Windows 2000 classic UI theme

---

## Setup (Development)

### Prerequisites
- Node.js 18 or later
- npm

### Install
```bash
npm install
```

### Run (development)
```bash
npm start
```

---

## Building Executables

### Windows (.exe installer + portable)
```bash
npm run build:win
```
Outputs to `dist/`:
- `GrassKit Setup 1.0.0.exe` — NSIS installer
- `GrassKit 1.0.0.exe` — portable (no install needed)

### Mac (.dmg + .app)
```bash
npm run build:mac
```
Outputs to `dist/`:
- `GrassKit-1.0.0.dmg` — drag-to-Applications installer
- `GrassKit-1.0.0-mac.zip` — zipped .app

> **Note:** Mac builds are unsigned by default. On first open, users need to right-click → Open to bypass Gatekeeper. Code signing requires an Apple Developer account and a Mac.

### Linux (.AppImage + .deb)
```bash
npm run build:linux
```

### All platforms at once
```bash
npm run build:all
```

> **Cross-compiling note:** You can build the Windows .exe from any OS. Building the Mac .dmg from Windows/Linux works for unsigned builds. For a fully signed Mac release, build on a Mac with an Apple Developer certificate.

---

## Assets
Place the following in the `assets/` folder:
- `icon.png` — 512×512 PNG app icon
- `icon.ico` — Windows icon (can convert from PNG at icoconvert.com)
- `icon.icns` — Mac icon (can convert from PNG at cloudconvert.com)

If icons are missing, electron-builder will use a default icon.

---

## File Structure
```
grasskit/
├── main.js          ← Electron main process
├── index.html       ← App UI (all HTML/CSS/JS)
├── package.json     ← Build config
├── assets/
│   ├── icon.png
│   ├── icon.ico
│   └── icon.icns
└── dist/            ← Built executables (generated)
```

---

## Using GrassKit
1. Upload your greyscale texture (or use Grass Side Mode for compositing)
2. Upload `grass.png` and/or `foliage.png` from:
   `resource_packs/vanilla/textures/colormap/`
3. Pick a biome from the list or use Manual mode
4. Optionally upload a tint mask
5. Click **Apply Tint**
6. Click **Save PNG** to export

---

*GamLo Studios — grasskit v1.0.0*
