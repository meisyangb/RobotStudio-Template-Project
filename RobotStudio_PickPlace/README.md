# PickPlace 拾取与放置模板

[![Version](https://img.shields.io/badge/Version-1.0.0-blue)](./CHANGELOG.md)
[![Complexity](https://img.shields.io/badge/Complexity-Intermediate-yellow)](./README.md)
[![Robot](https://img.shields.io/badge/Robot-IRB%201200-orange)](https://new.abb.com/products/robotics/industrial-robots/irb-1200)

## 项目简介

**PickPlace** 是一个完整的 ABB 机器人拾取与放置应用模板，专为物料搬运、装配和分拣任务设计。本模板提供了开箱即用的解决方案，包含完整的工作站配置、RAPID 程序代码和系统参数设置。

### 核心功能

- 📦 **智能拾取**：基于真空吸盘的物料拾取系统
- 🎯 **精确定位**：多点位循环作业，支持动态位置调整
- 🔄 **自动循环**：完整的自动化作业流程
- 🛡️ **安全保护**：碰撞检测和异常处理机制

---

## 技术栈说明

### 硬件配置

| 组件 | 型号 | 说明 |
|-----|------|------|
| 机器人 | IRB 1200-7/0.7 | 7kg 负载，0.7m 臂展 |
| 控制器 | IRC5 | RobotWare 6.08 |
| 工具 | 真空吸盘 | 自定义 VentosaTool |
| 通信 | Profinet | 与 PLC 通信 |

### 软件环境

```
RobotWare: 6.08.0130
RobotStudio: 2020.3 或更高版本
RAPID Language: 6.x
Communication: Profinet, Ethernet/IP
```

### 技术特点

- **模块化架构**：程序分为多个模块，便于维护
- **参数化配置**：关键参数集中管理
- **状态机设计**：清晰的程序状态流转
- **错误处理**：完善的异常处理机制

---

## 安装步骤

### 前提条件

1. 安装 ABB RobotStudio 2020 或更高版本
2. 确保拥有有效的 RobotWare 许可证
3. 克隆本仓库到本地

### 安装流程

1. **打开解决方案**
   ```
   文件 → 打开 → 解决方案
   选择: ABB_Pick&Place_v1.0.rssln
   ```

2. **加载工作站**
   - 工作站将自动加载
   - 虚拟控制器自动启动

3. **验证配置**
   ```
   控制器 → 虚拟控制器 → 配置
   检查 I/O 配置和系统参数
   ```

4. **运行测试**
   - 切换到 `自动` 模式
   - 点击 `播放` 按钮
   - 观察机器人执行拾取与放置动作

---

## 使用示例

### 基础操作

```rapid
! 主程序入口
PROC main()
    ! 初始化
    Initialize;
    
    ! 主循环
    WHILE TRUE DO
        ! 拾取物料
        PickObject pickPos;
        
        ! 移动到放置位置
        MoveJ placePos, v1000, fine, tool0;
        
        ! 放置物料
        PlaceObject placePos;
        
        ! 返回安全位置
        MoveJ homePos, v1000, fine, tool0;
    ENDWHILE
ENDPROC
```

### 自定义位置

```rapid
! 修改拾取位置
CONST robtarget pickPos := [[x, y, z], [q1, q2, q3, q4], [cfg1, cfg4, cfg6], [eaxA, eaxB, eaxC, eaxD, eaxE, eaxF]];

! 修改放置位置
CONST robtarget placePos := [[x, y, z], [q1, q2, q3, q4], [cfg1, cfg4, cfg6], [eaxA, eaxB, eaxC, eaxD, eaxE, eaxF]];
```

### I/O 控制示例

```rapid
! 打开真空
SetDO doVacuum, 1;
WaitTime 0.5;

! 检查真空反馈
IF DIVacuum = 1 THEN
    TPWrite "真空建立成功";
ELSE
    TPWrite "真空建立失败";
    Stop;
ENDIF
```

---

## 配置说明

### 系统参数配置

#### I/O 配置 (EIO.cfg)

```
- DI_01: 真空反馈输入
- DO_01: 真空控制输出
- DI_02: 物料检测传感器
- DO_02: 指示灯控制
```

#### 运动配置 (MOC.cfg)

```
- 速度限制: 1000 mm/s
- 加速度: 5000 mm/s²
- 工具负载: 2 kg
- 工作区域: 600mm x 400mm x 300mm
```

### 工具配置

**VentosaTool（真空吸盘）**

```rapid
PERS tooldata tVentosa:=[TRUE,[[0,0,100],[1,0,0,0]],[2,[0,0,50],[1,0,0,0],0,0,0]];
```

参数说明：
- 工具重量: 2 kg
- TCP 位置: Z 轴偏移 100mm
- 重心位置: Z 轴偏移 50mm

---

## 项目结构

```
RobotStudio_PickPlace/
├── 📄 README.md                    # 本文件
├── 📄 ABB_Pick&Place_v1.0.rssln    # 解决方案文件
│
├── 📁 Stations/                    # 工作站文件
│   └── ABB_Pick&Place_v1.0.rsstn   # 工作站配置
│
├── 📁 Libraries/                   # 工具库
│   └── VentosaTool.rslib           # 真空吸盘工具
│
├── 📁 Backups/                     # 控制器备份
│   └── Controller_Pick_Place_1/
│       ├── RAPID/                  # RAPID 程序
│       │   └── TASK1/
│       │       ├── PROGMOD/        # 程序模块
│       │       │   ├── CalibData.mod   # 校准数据
│       │       │   └── Module1.mod     # 主程序
│       │       └── SYSMOD/         # 系统模块
│       └── SYSPAR/                 # 系统参数
│           ├── EIO.cfg             # I/O 配置
│           ├── MOC.cfg             # 运动配置
│           ├── SIO.cfg             # 串口配置
│           └── SYS.cfg             # 系统配置
│
└── 📁 Systems/                     # 虚拟控制器系统
    └── Controller_Pick_Place_1/
        ├── INTERNAL/               # 内部文件
        ├── PRODUCTS/               # 产品配置
        └── HOME/                   # 用户文件
```

---

## 注意事项

### 安全警告

⚠️ **重要提示**：

1. **碰撞风险**
   - 首次运行前请使用 `手动` 模式测试
   - 确认所有安全区域设置正确
   - 检查工具和工作对象坐标系

2. **真空系统**
   - 确保真空泵压力达到 0.6 MPa 以上
   - 定期检查吸盘磨损情况
   - 监控真空反馈信号

3. **速度限制**
   - 调试阶段建议速度不超过 50%
   - 确认轨迹无干涉后再全速运行

### 使用限制

- 最大负载: 7 kg（含工具）
- 工作半径: 700 mm
- 重复定位精度: ±0.02 mm
- 环境温度: 5°C - 45°C

### 故障排除

| 问题 | 可能原因 | 解决方案 |
|-----|---------|---------|
| 真空无法建立 | 气源不足 | 检查气压和气管连接 |
| 定位偏差 | 工具坐标错误 | 重新校准工具坐标系 |
| 程序中断 | I/O 信号异常 | 检查传感器和接线 |
| 运动异常 | 关节限位 | 检查程序中的目标点 |

---

## 版本历史

### v1.0.0 (2026-04-21)

**新增功能**：
- ✨ 初始版本发布
- 🤖 完整的 PickPlace 工作站
- 🛠️ VentosaTool 真空吸盘工具
- 📋 模块化 RAPID 程序架构
- ⚙️ 完整的系统配置

**技术规格**：
- RobotWare 6.08
- IRB 1200-7/0.7 机器人
- Profinet 通信

### 计划更新

**v1.1.0 (计划中)**
- 添加视觉引导功能
- 支持多工件类型
- 优化运动轨迹

**v1.2.0 (计划中)**
- 添加力控功能
- 支持协作模式
- 集成 PLC 通信示例

---

## 相关资源

### 文档链接

- [根目录 README](../README.md) - 仓库整体介绍
- [CONTRIBUTING.md](../CONTRIBUTING.md) - 贡献指南
- [PUSH_LIMITS.md](../.github/PUSH_LIMITS.md) - 推送限制

### 外部资源

- [ABB RobotStudio 官方文档](https://new.abb.com/products/robotics/robotstudio)
- [IRB 1200 产品手册](https://new.abb.com/products/robotics/industrial-robots/irb-1200)
- [RAPID 指令参考](https://library.e.abb.com/public/688894b98123f87bc1257cc50044e809/Technical%20reference%20manual_RAPID.pdf)

---

## 维护与支持

### 维护者

- **主要维护者**: [@meisyangb](https://github.com/meisyangb)
- **最后更新**: 2026-04-21
- **版本**: v1.0.0

### 报告问题

如发现 bug 或有改进建议，请：

1. [创建 Issue](https://github.com/meisyangb/RobotStudio-Template-Project/issues)
2. 描述问题详情和复现步骤
3. 附上相关日志和截图

### 贡献代码

欢迎提交 Pull Request！请确保：

- 代码符合项目规范
- 通过所有测试
- 更新相关文档

---

**免责声明**: 本模板仅供学习和参考使用。在实际应用前，请根据具体需求进行充分测试和验证。
