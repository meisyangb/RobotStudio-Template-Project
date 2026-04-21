# RobotStudio 模板项目仓库

[![GitHub](https://img.shields.io/badge/GitHub-RobotStudio--Template--Project-blue)](https://github.com/meisyangb/RobotStudio-Template-Project)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![ABB](https://img.shields.io/badge/ABB-RobotStudio-orange)](https://new.abb.com/products/robotics/robotstudio)

## 仓库概述

本仓库是一个综合性的 **ABB RobotStudio 模板项目集合**，旨在为工业机器人应用开发提供标准化、可复用的项目模板。无论您是初学者还是经验丰富的工程师，都可以通过这些模板快速启动您的机器人项目。

### 核心目标

- 🚀 **快速启动**：减少项目初始化时间，直接开始业务开发
- 📚 **最佳实践**：提供符合行业标准的项目结构和代码规范
- 🔄 **可复用性**：模块化设计，便于在不同项目间复用
- 📖 **学习资源**：详细的文档和示例，帮助学习 RobotStudio 开发

---

## 模板项目分类

### 当前可用模板

| 模板名称 | 类型 | 适用场景 | 复杂度 |
|---------|------|---------|--------|
| [PickPlace](./RobotStudio_PickPlace) | 拾取与放置 | 物料搬运、装配、分拣 | ⭐⭐ 中级 |

### 规划中模板

| 模板名称 | 类型 | 适用场景 | 预计发布时间 |
|---------|------|---------|------------|
| Welding | 焊接 | 弧焊、点焊应用 | 2026 Q3 |
| Palletizing | 码垛 | 物流码垛、拆垛 | 2026 Q3 |
| MachineTending | 机床上下料 | CNC 上下料、加工中心 | 2026 Q4 |
| Painting | 喷涂 | 表面喷涂、涂胶 | 2026 Q4 |
| Assembly | 精密装配 | 零件装配、拧紧 | 2027 Q1 |

---

## 各项目适用场景

### 🤖 PickPlace（拾取与放置）

**适用行业**：
- 电子制造（PCB 组装、芯片搬运）
- 食品加工（包装、分拣）
- 物流仓储（包裹分拣、货物搬运）
- 汽车制造（零部件装配）

**核心功能**：
- 真空吸盘工具配置
- 视觉引导定位
- 多点位循环作业
- 安全碰撞检测

**技术特点**：
- 支持多种通信协议（Profinet、Ethernet/IP）
- 模块化 RAPID 程序架构
- 完整的 I/O 配置示例

---

## 快速开始指南

### 环境要求

```
必需：
├── ABB RobotStudio 2020 或更高版本
├── RobotWare 6.08 或更高版本
└── Windows 10/11 操作系统

推荐：
├── 虚拟控制器许可证（用于离线仿真）
├── 3D 鼠标（用于工作站导航）
└── 双显示器（提高效率）
```

### 使用步骤

1. **克隆仓库**
   ```bash
   git clone https://github.com/meisyangb/RobotStudio-Template-Project.git
   cd RobotStudio-Template-Project
   ```

2. **选择模板项目**
   ```bash
   # 查看可用模板
   ls -la
   
   # 进入所需模板目录
   cd RobotStudio_PickPlace
   ```

3. **打开项目**
   - 启动 RobotStudio
   - 选择 `文件` > `打开` > `解决方案`
   - 导航到模板目录，选择 `.rssln` 文件

4. **开始使用**
   - 查看子目录中的 `README.md` 获取详细使用说明
   - 根据您的需求修改配置
   - 运行仿真测试

---

## 项目结构

```
RobotStudio-Template-Project/
├── 📁 RobotStudio_PickPlace/          # PickPlace 模板项目
│   ├── 📄 README.md                    # 项目专属文档
│   ├── 📁 Stations/                    # 工作站文件
│   ├── 📁 Libraries/                   # 工具库
│   ├── 📁 Backups/                     # 控制器备份
│   └── 📁 Systems/                     # 虚拟控制器系统
│
├── 📁 .github/                         # GitHub 配置
│   └── 📄 PUSH_LIMITS.md               # 推送限制说明
│
├── 📄 README.md                        # 本文件（仓库级文档）
├── 📄 CONTRIBUTING.md                  # 贡献指南
├── 📄 LICENSE                          # 许可证
└── 📄 .gitignore                       # Git 忽略规则
```

---

## 贡献规范

我们欢迎所有形式的贡献！请遵循以下规范：

### 贡献流程

1. **Fork 仓库** - 创建您自己的分支
2. **创建功能分支** - `git checkout -b feature/YourFeature`
3. **提交更改** - 遵循 [Conventional Commits](https://www.conventionalcommits.org/) 规范
4. **推送分支** - `git push origin feature/YourFeature`
5. **创建 Pull Request** - 描述您的更改

### 提交信息规范

```
<type>(<scope>): <subject>

<body>

<footer>
```

**类型说明**：
- `feat`: 新功能
- `fix`: 修复
- `docs`: 文档
- `style`: 格式
- `refactor`: 重构
- `test`: 测试
- `chore`: 构建/工具

详细规范请查看 [CONTRIBUTING.md](./CONTRIBUTING.md)

---

## 文档维护说明

### 更新策略

当添加新模板项目时，请按以下顺序更新文档：

1. **创建子目录文档**
   - 在模板项目根目录创建 `README.md`
   - 遵循[子目录文档模板](#子目录文档模板)

2. **更新根目录 README**
   - 在"模板项目分类"表格中添加新项目
   - 在"各项目适用场景"部分添加项目介绍
   - 更新"项目结构"树状图

3. **更新导航链接**
   - 确保所有内部链接正确
   - 测试文档导航流畅性

### 文档规范

#### Markdown 格式

- 使用 `#` 表示标题层级
- 代码块使用三个反引号，并标注语言
- 列表使用 `-` 或数字序号
- 链接使用相对路径

#### 命名规范

- 文件夹：PascalCase（如 `RobotStudio_PickPlace`）
- 文件：kebab-case（如 `push-limits.md`）
- 图片：descriptive-name.png

### 版本管理

文档版本与代码版本同步：

```
文档版本格式：v<主版本>.<次版本>.<修订版本>

示例：
- v1.0.0 - 初始文档发布
- v1.1.0 - 新增模板项目
- v1.1.1 - 文档错误修正
```

---

## 支持与反馈

### 获取帮助

- 📖 **文档问题**：查看各项目的 `README.md`
- 🐛 **Bug 报告**：[创建 Issue](https://github.com/meisyangb/RobotStudio-Template-Project/issues)
- 💡 **功能建议**：[发起讨论](https://github.com/meisyangb/RobotStudio-Template-Project/discussions)
- 📧 **邮件联系**：meisyangb@example.com

### 社区资源

- [ABB RobotStudio 官方文档](https://new.abb.com/products/robotics/robotstudio)
- [RAPID 语言参考手册](https://library.e.abb.com/public/688894b98123f87bc1257cc50044e809/Technical%20reference%20manual_RAPID.pdf)
- [RobotStudio 论坛](https://forums.robotstudio.com/)

---

## 许可证

本项目采用 [MIT 许可证](LICENSE) - 详见 LICENSE 文件。

```
MIT License

Copyright (c) 2026 meisyangb

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 更新日志

### v1.0.0 (2026-04-21)

- ✨ 初始发布
- 🤖 添加 PickPlace 模板项目
- 📚 创建完整文档体系
- 🔧 建立贡献规范

---

**维护者**：[@meisyangb](https://github.com/meisyangb)  
**最后更新**：2026-04-21  
**文档版本**：v1.0.0
