# RobotStudio 模板项目

[![GitHub](https://img.shields.io/badge/GitHub-RobotStudio--Template--Project-blue)](https://github.com/meisyangb/RobotStudio-Template-Project)

## 项目概述

这是一个 ABB RobotStudio 拾取与放置（Pick and Place）项目模板。它为使用 ABB 工业机器人开发机器人拾取与放置应用提供了完整的基础框架。

## 项目结构

```
RobotStudio_PickPlace/
├── ABB_Pick&Place_v1.0.rssln          # RobotStudio 解决方案文件
├── Stations/
│   └── ABB_Pick&Place_v1.0.rsstn      # RobotStudio 工作站文件
├── Libraries/
│   └── VentosaTool.rslib              # 自定义工具库（真空吸盘）
├── Backups/
│   └── Controller_Pick_Place_1/       # 控制器备份文件
│       ├── RAPID/
│       │   └── TASK1/
│       │       └── PROGMOD/
│       │           ├── CalibData.mod  # 校准数据模块
│       │           └── Module1.mod    # 主程序模块
│       └── SYSPAR/                    # 系统参数
│           ├── EIO.cfg                # I/O 配置
│           ├── MOC.cfg                # 运动配置
│           ├── SIO.cfg                # 串口 I/O 配置
│           └── SYS.cfg                # 系统配置
└── Systems/
    └── Controller_Pick_Place_1/       # 虚拟控制器系统
```

## 功能特性

- 🤖 **完整的拾取与放置解决方案**：可直接使用的拾取与放置操作模板
- 🛠️ **自定义工具库**：包含真空吸盘（VentosaTool）配置
- 📋 **RAPID 程序**：预配置的 RAPID 模块，包含校准数据
- ⚙️ **系统配置**：完整的 I/O、运动和系统参数设置
- 💾 **备份支持**：完整的控制器备份，便于恢复

## 系统要求

- ABB RobotStudio 2020 或更高版本
- RobotWare 6.x 或更高版本
- 虚拟控制器许可证（用于仿真）

## 快速开始

1. **克隆仓库**
   ```bash
   git clone https://github.com/meisyangb/RobotStudio-Template-Project.git
   ```

2. **在 RobotStudio 中打开**
   - 打开 RobotStudio
   - 选择 `文件` > `打开` > `解决方案`
   - 导航到 `RobotStudio_PickPlace/ABB_Pick&Place_v1.0.rssln`

3. **加载工作站**
   - 工作站文件 `ABB_Pick&Place_v1.0.rsstn` 将自动加载
   - 虚拟控制器将以预配置设置启动

4. **运行程序**
   - 切换到 `自动` 模式
   - 按 `播放` 按钮开始仿真

## 贡献指南

请阅读 [CONTRIBUTING.md](CONTRIBUTING.md) 了解我们的行为准则和提交拉取请求的流程。

## 推送限制

请阅读 [.github/PUSH_LIMITS.md](.github/PUSH_LIMITS.md) 了解推送要求和限制。

## 许可证

本项目采用 MIT 许可证 - 详见 LICENSE 文件。

## 联系方式

如有问题或需要支持，请在 GitHub 上提交 issue。

---

**注意**：这是一个模板项目。请根据您的具体应用需求进行定制。
