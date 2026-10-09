RealScene-Viewpoint-Consensus

This repository contains a processed, scene-organized dataset for viewpoint evaluation and viewpoint-consensus analysis in real-scene 3D models. Each scene contains viewpoint evaluation records and the viewpoint clusters derived from those records.

## Repository layout

```text
FINAL-DATA/
├── HK-001/
│   └── user_test/
│       ├── user_view_clusters.json
│       └── user_view_evaluations.jsonl
├── ...
├── HK-150/
├── WHU-01/
└── WHU-50/
```

- The dataset contains 200 scene directories: `HK-001`–`HK-150` and `WHU-01`–`WHU-50`.
- Each scene contains one `user_test` directory.
- Each scene contains 100 viewpoint-evaluation records, for a total of 20,000 records.
- The `scene_name` stored in each file matches its scene directory name.

## File formats

### `user_view_evaluations.jsonl`

This is a JSON Lines file with one viewpoint-evaluation record per line. The main fields are:

- `scene_name`: scene identifier.
- `evaluator`: anonymized evaluator identifier.
- `confidence`: evaluation confidence value.
- `u`, `v`: view-position parameters in the scene view.
- `eye`: camera-position coordinates.
- `target`: target-point coordinates.
- `direction`: viewing-direction vector.
- `azimuth_deg`: azimuth angle in degrees.
- `elevation_deg`: elevation angle in degrees.

### `user_view_clusters.json`

This JSON file stores the scene-level viewpoint-clustering results. The main fields are:

- `scene_name`: scene identifier.
- `evaluation_count`: number of evaluation records used for clustering.
- `auto_cluster_count`: automatically selected number of clusters.
- `clusters`: all clusters, including their members, centers, and statistics.
- `top3_clusters`: the highest-ranked three clusters, or fewer when the scene contains fewer than three clusters.
- `weighted_silhouette`: weighted silhouette coefficient for the scene.
