# Just Dance AvatarAnimator — v2.0.0

A standalone browser-based 2D animation workspace built with vanilla HTML, CSS and JavaScript. No build step and no runtime library dependency are required.

## Run locally
Open `index.html` in a modern browser, or serve this folder:

```bash
python -m http.server 8000
```

Visit `http://localhost:8000`.

## GitHub Pages
1. Create a repository named `just-dance-avatar-animator`.
2. Upload the contents of this folder to the repository root.
3. Go to **Settings → Pages**.
4. Choose **Deploy from a branch**, `main`, and `/ (root)`.

## Available in v2.0
- Image import (PNG, JPG, WebP and browser-supported image formats)
- Canvas selection and transform controls: position, scale, rotation, opacity
- Pen polygon masks (multiple polygons) and movable anchor point
- Bone and pin placement with a sequential chain data structure
- Transform and turbulence keyframes with linear, ease-in, ease-out, smooth and overshoot interpolation
- Frame timeline, FPS selection, loop playback and scrubbing
- Turbulence displacement preview
- Project save and restore (`.project.json`, includes embedded artwork)
- PNG sprite sheet export
- Offline GIF89a export with a built-in palette/LZW encoder
- WebM recording and MP4 where the browser provides an MP4 MediaRecorder codec
- Local SVG tool icons in `assets/icons/`

## Known engineering boundaries
This release is a functional 2D animation starter, not a production-grade replacement for After Effects or Blender. Bone placement, pins and chain grouping are implemented as rig data and viewport overlays; full mesh skinning, weight painting, inverse kinematics, and smart-bone-driven mesh deformation are not implemented yet. Polygon masks clip the artwork to the union of drawn polygons; they do not yet provide subtractive paths or independent cut-out layers. Turbulence is a canvas displacement effect and may be CPU-intensive on large images. Transparent video depends on browser and codec support; MP4 generally does not carry alpha, so WebM is the preferred transparent-video candidate. GIF uses a compact 3-3-2 palette and exports a reduced-resolution animation for reasonable file sizes.

## Compatibility
Use a current desktop version of Chrome, Edge or Firefox for the best experience. File saving, canvas recording and codecs depend on browser capabilities. For local file access and GitHub Pages, use HTTPS or localhost.
