# MoJoint 关节电机项目

> 一款面向机器人关节的模块化电机系统，涵盖电机本体、驱动器硬件、驱动器固件以及上位机工具链。

## 项目简介

MoJoint 致力于打造一款高性能、模块化的机器人关节电机解决方案。项目覆盖从机械设计到软件工具的完整链路，主要包括：

- **电机本体设计**：关节电机的机械结构、电磁与热设计。
- **电机驱动器设计**：驱动器硬件原理图、PCB 与电源方案。
- **驱动器固件设计**：电机控制算法、通信协议与嵌入式软件。
- **上位机工具链**：基于 ROS2 的接口节点与 QT 可视化上位机。

本仓库作为项目的顶层管理仓库，通过 Git Submodule 统筹各子模块仓库，维护整体文档、追踪里程碑与发布版本。

## 功能特性

- 完整的关节电机软硬件参考设计
- 模块化子仓库管理，便于独立开发与版本控制
- 支持 ROS2 与 QT 上位机的实时调试与监控
- 统一的文档入口与版本发布记录

## 仓库结构

```text
MoJoint/
├── README.md                 # 项目总览（本文件）
├── docs/                     # 项目文档（架构、协议、开发指南）
├── MoJoint_Hardware/         # 驱动器硬件设计子仓库
├── MoJoint_Firmware/         # 驱动器固件子仓库
├── MoJoint_Mechanics/        # 电机机械本体设计子仓库
└── MoJoint_Tools/            # 上位机工具链子仓库（待接入）
```

## 快速开始

### 克隆项目（包含所有子仓库）

```bash
git clone --recursive git@github.com:zagerx/MoJoint.git
cd MoJoint
```

### 已克隆主仓库，单独拉取子仓库

```bash
cd MoJoint
git submodule update --init --recursive
```

### 文档入口

- [版本发布说明](./docs/release-notes.md)
- [项目架构](./docs/architecture.md)（待补充）
- [开发环境搭建](./docs/development.md)（待补充）
- [通信协议](./docs/protocol.md)（待补充）

## 子仓库管理

当前已接入的子仓库：

| 子仓库 | 本地路径 | 说明 |
|--------|----------|------|
| `MoJoint_Hardware` | `MoJoint_Hardware/` | 驱动器硬件设计 |
| `MoJoint_Firmware` | `MoJoint_Firmware/` | 驱动器固件 |
| `MoJoint_Mechanics` | `MoJoint_Mechanics/` | 电机机械本体设计 |

### 新增子仓库

```bash
git submodule add git@github.com:zagerx/<RepoName>.git <RepoName>
git add .gitmodules <RepoName>
git commit -m "chore: 接入子模块<RepoName>"
```

### 更新所有子仓库到最新提交

```bash
git submodule update --remote
```

---

如有问题，欢迎通过 [Issues](../../issues) 进行交流。
