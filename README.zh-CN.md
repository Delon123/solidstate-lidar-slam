# solidstate-lidar-slam

[![License: GPL v2](https://img.shields.io/badge/License-GPLv2-blue.svg)](LICENSE)
[![Stars](https://img.shields.io/github/stars/JokerJohn/solidstate-lidar-slam?style=social)](https://github.com/JokerJohn/solidstate-lidar-slam/stargazers)
[![Issues](https://img.shields.io/github/issues/JokerJohn/solidstate-lidar-slam)](https://github.com/JokerJohn/solidstate-lidar-slam/issues)

默认文档见 [README.md](README.md)

> 面向固态面阵激光雷达的 LIO/LVIO/SLAM 适配与评测仓库，重点覆盖小角度短距与退化场景鲁棒性问题。

## 目录

- [项目概述](#项目概述)
- [范围定义](#范围定义)
- [已适配算法](#已适配算法)
- [退化场景重点](#退化场景重点)
- [仓库结构](#仓库结构)
- [路线图](#路线图)
- [引用建议](#引用建议)
- [上游仓库引用](#上游仓库引用)
- [许可证](#许可证)

## 项目概述

`solidstate-lidar-slam` 用于统一组织固态面阵激光雷达在多类 LIO/LVIO/SLAM 算法中的适配与评测工作。

当前发布状态：

- 仓库框架已公开。
- 各算法适配模块按里程碑逐步开放。
- 退化场景处理方案统一维护在 `docs/degenerate-scenarios/`。

## 范围定义

当前覆盖：

- 多算法后端的统一适配入口与模块组织。
- 面向小角度短距固态雷达的参数基线。
- 退化场景处理策略与评测规范。

当前不覆盖：

- 声称完整重写全部上游算法。
- 替代上游论文与官方文档。

## 已适配算法

| 算法 | 类别 | 集成状态 | 上游仓库 | 上游许可证 |
| --- | --- | --- | --- | --- |
| FAST-LIO2 | LIO | 已完成内部适配，代码逐步开放 | [hku-mars/FAST_LIO](https://github.com/hku-mars/FAST_LIO) | GPL-2.0 |
| FAST-LIVO2 | LVIO | 已完成内部适配，代码逐步开放 | [hku-mars/FAST-LIVO2](https://github.com/hku-mars/FAST-LIVO2) | GPL-2.0 |
| COIN-LIO | LIO | 已完成内部适配，代码逐步开放 | [ethz-asl/COIN-LIO](https://github.com/ethz-asl/COIN-LIO) | BSD-3-Clause（上游 LICENSE 含 GPLv2 说明） |
| Direct-LIO | LIO | 已完成内部适配，代码逐步开放 | [vectr-ucla/direct_lidar_inertial_odometry](https://github.com/vectr-ucla/direct_lidar_inertial_odometry) | MIT |
| Voxel-SLAM | SLAM | 已完成内部适配，代码逐步开放 | [hku-mars/Voxel-SLAM](https://github.com/hku-mars/Voxel-SLAM) | GPL-2.0 |
| VoxelMap | SLAM | 已完成内部适配，代码逐步开放 | [hku-mars/VoxelMap](https://github.com/hku-mars/VoxelMap) | 上游 README 声明 GPLv2 |

## 退化场景重点

核心场景分类（维护于 `docs/degenerate-scenarios/`）：

- `Low-Texture`
- `Repetitive Geometry`
- `Narrow FoV`
- `Dynamic Interference`

## 仓库结构

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

## 路线图

- [ ] 发布 6 类算法的最小可运行适配基线。
- [ ] 补充小角度短距固态雷达参数模板。
- [ ] 建立退化场景评测协议与报告模板。
- [ ] 提供跨算法复现实验样例。

## 引用建议

若本仓库对你的研究或工程有帮助，建议：

- 在论文/报告中优先引用对应上游算法工作。
- 将本仓库作为适配流程与评测基线的工程引用。

## 上游仓库引用

- FAST-LIO2: <https://github.com/hku-mars/FAST_LIO>
- FAST-LIVO2: <https://github.com/hku-mars/FAST-LIVO2>
- COIN-LIO: <https://github.com/ethz-asl/COIN-LIO>
- Direct-LIO: <https://github.com/vectr-ucla/direct_lidar_inertial_odometry>
- Voxel-SLAM: <https://github.com/hku-mars/Voxel-SLAM>
- VoxelMap: <https://github.com/hku-mars/VoxelMap>

## 许可证

本仓库采用 **GPL-2.0**。

多上游适配场景下的许可证映射与合规说明见 [THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md)。
