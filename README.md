# MoJoint 关节电机项目

> 一款面向机器人关节的模块化电机系统，涵盖电机本体、驱动器硬件、驱动器固件以及上位机工具链。

## 项目简介

MoJoint 致力于打造一款高性能、模块化的机器人关节电机解决方案。项目覆盖从机械设计到软件工具的完整链路，主要包括：

- **电机本体设计**：关节电机的机械结构、电磁与热设计。
- **电机驱动器设计**：驱动器硬件原理图、PCB 与电源方案。
- **驱动器固件设计**：电机控制算法、通信协议与嵌入式软件。
- **上位机工具链**：基于 ROS2 的接口节点与 QT 可视化上位机。

本仓库作为项目的顶层管理仓库，用于统筹各子模块仓库、维护整体文档、追踪里程碑与发布版本。

## 功能特性

- 完整的关节电机软硬件参考设计
- 模块化子仓库管理，便于独立开发与版本控制
- 支持 ROS2 与 QT 上位机的实时调试与监控
- 开放的文档与协作流程

## 仓库结构

```text
MoJoint/
├── README.md                 # 项目总览（本文件）
├── docs/                     # 项目文档（架构、协议、开发指南）
├── mojoint-motor/            # 电机本体设计子仓库（机械/电磁）
├── mojoint-driver-hw/        # 驱动器硬件设计子仓库
├── mojoint-driver-fw/        # 驱动器固件子仓库
├── mojoint-tools-ros2/       # ROS2 接口工具子仓库
└── mojoint-tools-gui/        # QT 上位机子仓库
```

> 提示：当前子仓库尚未通过 Git Submodule 接入，后续可按照 [子仓库接入规范](#子仓库接入规范) 进行配置。

## 快速开始

### 克隆项目

```bash
git clone https://github.com/your-org/MoJoint.git
cd MoJoint
```

### 拉取子仓库（配置完成后）

```bash
git submodule update --init --recursive
```

### 文档入口

- [项目架构](./docs/architecture.md)
- [开发环境搭建](./docs/development.md)
- [通信协议](./docs/protocol.md)
- [版本发布说明](./docs/release-notes.md)

## 子仓库接入规范

为了保持项目结构清晰，建议后续通过 Git Submodule 管理各子模块：

```bash
git submodule add <子仓库地址> mojoint-motor
git submodule add <子仓库地址> mojoint-driver-hw
git submodule add <子仓库地址> mojoint-driver-fw
git submodule add <子仓库地址> mojoint-tools-ros2
git submodule add <子仓库地址> mojoint-tools-gui
```

并在 CI 或文档中提供 `git clone --recursive` 或 `git submodule update --init --recursive` 的说明。

---

如有问题，欢迎通过 [Issues](../../issues) 进行交流。
