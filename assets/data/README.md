# SafeAnchor-Grasp reported results

Updated: 2026-09-13.

Source: `real_artical92.tex`, mirrored at `../manuscript.tex`.

Source SHA-256: `4672295ed7f81dd03ead9c3fd2f88af9c6bea1a84b3bcd079198f4a2977ed09a`.

`results.json` contains manuscript-reported aggregates. It is not a release of trial-level logs, training samples, or the complete underlying benchmark dataset.

## Coverage

| JSON group | Manuscript location | Scope |
|---|---|---|
| `generator_adaptation` | Table I | Three grasp generators |
| `overall_performance` | Table II | DexGraspNet 2.0; 90 test scenes and low-success subsets |
| `bootstrap_intervals` | Sec. IV-C1 | Scene-level paired-bootstrap 95% intervals |
| `scene_examples` | Sec. IV-C1 | Four representative low-success scenes |
| `graspnet_benchmark` | Table III | All six reported methods; Dense, Random, Loose |
| `candidate_ceilings` | Sec. IV-A, IV-C2, Table IV-B | Separate training, validation, and test splits |
| `selection_behavior` | Sec. IV-C2 | DexGraspNet 2.0 test replacement statistics |
| `anchorlift_ablation` | Table IV-A | Diagnostic-scene component ablation |
| `gate_policy_ablation` | Table IV-B | DexGraspNet 2.0 intervention-policy comparison |
| `gate_validation_ablation` | Sec. IV-C3 | Three-seed validation-set component ablations |
| `real_robot_results` | Table V | Two settings, 100 attempts per method per setting |
| `protocol` | Sec. IV-A and IV-D | Simulation and real-robot evaluation protocols |
| `videos` | Author-selected materials | Videos 1-7, in author-specified order |

## Units and missing values

- Success rates, replacement rates, and ceilings are proportions unless the field name ends in `_percent`.
- `_percent` fields are on a 0-100 scale. `_pp` denotes percentage points, not relative percentage change.
- `per_1000` denotes events per 1,000 evaluated pairs.
- `reported_gain` retains the source's reported precision; it is not recomputed from rounded displayed means. For example, Table II reports 0.8921, 0.9221, and +0.0301. Subtracting the displayed rounded means produces 0.0300, while the reported gain is retained separately.
- Table I gains use the two-decimal reported success values: 0.15, 0.10, and 0.03.
- `null` means an unavailable or unreported result, never zero. The revised joint ceilings for DexDiffuser and GenDexGrasp have not been supplied. Their previous ceilings were below the updated selected success rates and are not used.
- DexDiffuser and GenDexGrasp replacement rates remain as reported in the current manuscript; this update does not recompute them from raw records.
- The approximately 12% replacement rate applies to the DexGraspNet 2.0 setting only. It is not a global rule shared by all generators or a per-scene cap.

## Evaluation boundaries

The 26 low-success scenes have Raw Grasp success below 0.85. Best-10 and best-6 are ranked by gain within those same 26 scenes, rather than independent test sets. Diagnostic-scene ablations and three-seed validation ablations must not be treated as evaluations on the full 90-scene test set.

The Raw-or-AnchorLift joint ceiling is an oracle result: it uses execution outcomes and is not a deployable selection policy.

The real-robot evaluation uses ten unseen everyday objects. Single-object testing uses ten randomized poses per object. Cluttered testing uses ten rounds of sequentially grasping and removing ten targets, with all starting poses randomized between rounds. A success requires stable lifting of the specified target by at least 0.10 m.

## Video encoding

The seven author-selected videos are published as H.264 MP4 web copies, with the MP4 index moved to the start for streaming. The original HEVC recordings are retained unchanged outside this repository. Conversion preserves each video's frame count, 1280 x 720 dimensions, order, and duration; no scene is cropped, trimmed, or retimed. Audio, when present, is encoded as AAC. `video_manifest.json` records original and web-copy hashes and media properties.
