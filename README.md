# solidstate-lidar-slam

[![License: GPL v2](https://img.shields.io/badge/License-GPLv2-blue.svg)](LICENSE)
[![Stars](https://img.shields.io/github/stars/JokerJohn/solidstate-lidar-slam?style=social)](https://github.com/JokerJohn/solidstate-lidar-slam/stargazers)
[![Issues](https://img.shields.io/github/issues/JokerJohn/solidstate-lidar-slam)](https://github.com/JokerJohn/solidstate-lidar-slam/issues)

中文文档请见 [README.zh-CN.md](README.zh-CN.md).

> Adapter and benchmark hub for solid-state LiDAR across LIO/LVIO/SLAM, focused on small-FoV short-range sensing and degenerate-scene robustness.

## Table of Contents

- [Overview](#overview)
- [Scope](#scope)
- [Supported Algorithms](#supported-algorithms)
- [Degenerate Scenario Focus](#degenerate-scenario-focus)
- [Repository Layout](#repository-layout)
- [Roadmap](#roadmap)
- [Citation](#citation)
- [Upstream References](#upstream-references)
- [License](#license)

## Overview

`solidstate-lidar-slam` provides a unified adaptation and benchmarking workspace for solid-state LiDAR pipelines.

Current release status:

- Repository structure is public.
- Algorithm adaptation modules are being released incrementally.
- Degenerate-scene handling notes are organized under `docs/degenerate-scenarios/`.

## Scope

In scope:

- Unified adaptation entry for multiple LIO/LVIO/SLAM backends.
- Configuration baselines for small-FoV short-range solid-state LiDAR.
- Degenerate-scene handling strategies and evaluation conventions.

Out of scope (at this stage):

- Claiming full reimplementation of all upstream projects.
- Replacing original upstream documentation and papers.

## Supported Algorithms

| Algorithm | Category | Integration Status | Upstream Repository | Upstream License |
| --- | --- | --- | --- | --- |
| FAST-LIO2 | LIO | Adapted internally, release in progress | [hku-mars/FAST_LIO](https://github.com/hku-mars/FAST_LIO) | GPL-2.0 |
| FAST-LIVO2 | LVIO | Adapted internally, release in progress | [hku-mars/FAST-LIVO2](https://github.com/hku-mars/FAST-LIVO2) | GPL-2.0 |
| COIN-LIO | LIO | Adapted internally, release in progress | [ethz-asl/COIN-LIO](https://github.com/ethz-asl/COIN-LIO) | BSD-3-Clause (with GPLv2 notice in upstream LICENSE) |
| Direct-LIO | LIO | Adapted internally, release in progress | [vectr-ucla/direct_lidar_inertial_odometry](https://github.com/vectr-ucla/direct_lidar_inertial_odometry) | MIT |
| Voxel-SLAM | SLAM | Adapted internally, release in progress | [hku-mars/Voxel-SLAM](https://github.com/hku-mars/Voxel-SLAM) | GPL-2.0 |
| VoxelMap | SLAM | Adapted internally, release in progress | [hku-mars/VoxelMap](https://github.com/hku-mars/VoxelMap) | GPLv2 stated in upstream README |

## Degenerate Scenario Focus

Primary scenario taxonomy (tracked in `docs/degenerate-scenarios/`):

- `Low-Texture`
- `Repetitive Geometry`
- `Narrow FoV`
- `Dynamic Interference`

## Repository Layout

```text
.
|-- README.md
|-- README.zh-CN.md
|-- LICENSE
|-- THIRD_PARTY_LICENSES.md
|-- docs/
|   |-- zh/
|   |-- en/
|   `-- degenerate-scenarios/
|-- modules/
|   |-- fast-lio2/
|   |-- fast-livo2/
|   |-- coin-lio/
|   |-- direct-lio/
|   |-- voxel-slam/
|   `-- voxelmap/
|-- configs/
|-- datasets/
`-- tools/
```

## Roadmap

- [ ] Publish runnable baseline adapters for all listed algorithms.
- [ ] Release parameter templates for small-FoV short-range sensors.
- [ ] Add benchmark protocol and reporting templates for degenerate scenarios.
- [ ] Provide reproducible examples for cross-algorithm comparison.

## Citation

If this repository is useful for your research or engineering project, please:

- Cite the corresponding upstream algorithms in your paper/report.
- Reference this repository for adaptation and benchmark workflows.

## Upstream References

- FAST-LIO2: <https://github.com/hku-mars/FAST_LIO>
- FAST-LIVO2: <https://github.com/hku-mars/FAST-LIVO2>
- COIN-LIO: <https://github.com/ethz-asl/COIN-LIO>
- Direct-LIO: <https://github.com/vectr-ucla/direct_lidar_inertial_odometry>
- Voxel-SLAM: <https://github.com/hku-mars/Voxel-SLAM>
- VoxelMap: <https://github.com/hku-mars/VoxelMap>

## License

This repository is licensed under **GPL-2.0**.

For multi-upstream adaptation details and per-project license mapping, see [THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md).
