# SafeAnchor-Grasp Project Page

Static project page for:

**SafeAnchor-Grasp: An Object Grasp Optimization Method for Cluttered Multi-Object Scenes**

## Files

- `index.html`: project page content.
- `styles.css`: page layout and responsive styling.
- `assets/manuscript.tex`: current manuscript source snapshot from `real_artical92.tex`, updated 2026-09-13. This source snapshot is not a standalone LaTeX compilation bundle.
- `assets/data/results.json`: all five manuscript tables, bootstrap intervals, representative scenes, candidate ceilings, selection statistics, validation ablations, and evaluation protocols.
- `assets/data/README.md`: units, provenance, rounding, and missing-data definitions.
- `assets/data/video_manifest.json`: source and web-file hashes, codecs, dimensions, frame counts, and durations for the seven videos.
- `assets/images/`: project figures and hero image.
- `assets/videos/1.mp4` through `assets/videos/7.mp4`: H.264 web copies of the seven author-selected real-robot experiment videos, in the supplied order. Original HEVC files are unchanged; frame counts, 1280 x 720 dimensions, and durations are preserved, with no cropping or time editing.
- Other existing `assets/videos/` files: earlier paired examples and archived demonstrations. The paired Raw Grasp / UR execution examples are preserved.

## Result scope

The cross-generator comparison reports gains of approximately 15, 10, and 3 percentage points for DexDiffuser, GenDexGrasp, and DexGraspNet 2.0. The detailed overall, low-success, candidate-selection, and intervention-policy results are specifically for DexGraspNet 2.0.

The approximately 12% replacement rate is an observed result for DexGraspNet 2.0, not a universal or per-scene budget. Missing joint ceilings for DexDiffuser and GenDexGrasp are explicitly recorded as `null` and displayed as `N/A`; no result has been inferred to fill these entries.

The JSON contains reported aggregate results, not trial-level logs or a complete raw dataset. Existing research figures are retained in this data/video update.

Open `index.html` directly in a browser, or run a local static server:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.
