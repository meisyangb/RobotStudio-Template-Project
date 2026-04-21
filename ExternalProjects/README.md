# 外部开源 ABB 项目集合

本目录包含从 GitHub 收集的开源 ABB RobotStudio 项目，用于学习、测试和参考。

## 项目清单

### 1. ABB_PALLETIZING_TEMPLATE ⭐ 推荐

**来源**: https://github.com/5RCM7/ABB_PALLETIZING_TEMPLATE

**项目类型**: 码垛模板

**适用版本**: 
- RobotWare: 6.08+
- RobotStudio: 2020.3+

**项目特点**:
- ✅ 完整的码垛解决方案
- ✅ 包含 FlexPendant WebApp 界面
- ✅ 支持单/双托盘配置
- ✅ 优化的 RAPID 代码结构
- ✅ 详细的安装和配置文档

**包含内容**:
```
ABB_PALLETIZING_TEMPLATE/
├── Rapid/                          # RAPID 程序模块
│   ├── PROGMOD/                    # 程序模块
│   │   ├── PalletizingTemplate.mod # 主程序
│   │   ├── RunCycle.mod            # 循环控制
│   │   └── Settings.mod            # 参数设置
│   └── SYSMOD/                     # 系统模块
│       └── PickPlaceItem.mod       # 拾取放置逻辑
├── Interface_flexpendant/          # FlexPendant 界面
│   ├── WebApp_1_Pallet/            # 单托盘版本
│   └── WebApp_2_Pallets/           # 双托盘版本
└── Palletize Template.rspag        # Pack&Go 文件
```

**使用建议**: 
- 适合作为码垛项目的起点
- 可根据需要选择单托盘或双托盘配置
- WebApp 界面可直接使用或定制

---

### 2. ABB-RobotStudio-SortingProductionLine ⭐⭐ 强烈推荐

**来源**: https://github.com/rparak/ABB-RobotStudio-SortingProductionLine

**项目类型**: 分拣产线（多机器人协作）

**适用版本**:
- RobotWare: 6.10 (IRB 1200), 7.2.1 (GoFa CRB 15000)
- RobotStudio: 2021.1.2+

**项目特点**:
- ✅ 多机器人协作示例
- ✅ 传送带控制系统
- ✅ 智能夹具和真空吸盘
- ✅ 完整的产线仿真
- ✅ 包含视频教程

**包含内容**:
```
ABB-RobotStudio-SortingProductionLine/
├── Solution_IRB_1200/              # IRB 1200 解决方案
│   ├── Final/
│   │   └── Solution_Sorting_Production_Line.rspag
│   ├── Rapid/
│   │   ├── T_ROB1/                 # 机器人1程序
│   │   └── T_ROB2/                 # 机器人2程序
│   └── Exe_file/                   # 可执行演示
├── Solution_CRB_15000_GoFa/        # GoFa 协作机器人方案
│   ├── Final/
│   ├── Rapid/
│   │   ├── Controller1/            # 控制器1
│   │   └── Controller2/            # 控制器2
│   └── Exe_file/
├── Template/                       # 空白模板
├── Project_Materials/              # 项目素材
│   ├── .rslib/                     # 工具库
│   └── .sat/                       # CAD 文件
└── images/                         # 文档图片
```

**使用建议**:
- 学习多机器人通信和协作
- 了解传送带与机器人的集成
- 参考智能夹具的实现方式

---

### 3. ABB-RobotStudio-Palletizer-Sorting_Pick-Place

**来源**: https://github.com/Maurilio97-P/ABB-RobotStudio-Palletizer-Sorting_Pick-Place

**项目类型**: 码垛 + 分拣（含教程）

**适用版本**:
- RobotWare: 6.08.01
- RobotStudio: 6.08.01
- 机器人: IRB 1660ID

**项目特点**:
- ✅ 完整的视频教程（4部分）
- ✅ 符合 ISO 10218 安全标准
- ✅ Smart Components 使用示例
- ✅ 安全设备集成（光幕、急停）
- ✅ World Zones 安全区域

**包含内容**:
```
ABB-RobotStudio-Palletizer-Sorting_Pick-Place/
├── ABB_Pick&Place_v1.0.rspag       # Pack&Go 文件
├── ABB_Pick&Place_v1.0.rssln       # 解决方案文件
├── Backups/                        # 控制器备份
│   └── Controller_Pick_Place_1/
├── Documents/                      # 文档资料
│   ├── ISO 10218.pptx              # 安全标准
│   ├── Pick and place tutorial.txt # 教程文本
│   └── Robotstudio basics.txt      # 基础教程
└── Geometry/                       # 几何模型
    ├── Grippers/                   # 夹具模型
    └── Safety Devices/             # 安全设备
```

**教程内容**:
1. **Part 1**: Smart Components 吸盘制作
2. **Part 2**: Smart Components 传送带
3. **Part 3**: Work Objects 和 Pick&Place
4. **Part 4**: ISO 10218 安全措施

**视频教程**: https://youtu.be/y0FjnO8AysQ

**使用建议**:
- 适合初学者学习 RobotStudio 基础
- 了解安全标准和实施
- 学习 Smart Components 的使用

---

### 4. RAPID-Scripts-and-Demos ⭐ 实用脚本

**来源**: https://github.com/FLo-ABB/RAPID-Scripts-and-Demos

**项目类型**: RAPID 脚本和示例

**适用版本**:
- RobotWare: 6.x+
- RobotStudio: 2020+

**项目特点**:
- ✅ 实用的 RAPID 模块
- ✅ TCP 校准工具
- ✅ PickPlace 功能模块
- ✅ 循环时间测量
- ✅ 代码简洁易懂

**包含内容**:
```
RAPID-Scripts-and-Demos/
├── ToolCenterCalculations/         # TCP 校准
│   └── SphereFit.mod               # 球面拟合方法
├── PickPlace/                      # 拾取放置
│   ├── PickPlace.mod               # 基础功能
│   └── MatrixPickPlace.mod         # 矩阵拾取
├── CycleTime/                      # 循环时间
│   └── CycleTime.mod               # 计时模块
└── README.md                       # 使用说明
```

**使用建议**:
- 作为功能模块集成到项目中
- 学习 RAPID 编程技巧
- 快速实现常用功能

---

## 版本兼容性说明

| 项目 | RobotWare | RobotStudio | 机器人型号 |
|------|-----------|-------------|-----------|
| ABB_PALLETIZING_TEMPLATE | 6.08+ | 2020.3+ | 通用 |
| SortingProductionLine | 6.10/7.2.1 | 2021.1.2+ | IRB 1200, GoFa |
| Palletizer-Sorting | 6.08.01 | 6.08.01 | IRB 1660ID |
| RAPID-Scripts | 6.x+ | 2020+ | 通用 |

## 使用建议

### 对于 RobotWare 6.08 / RobotStudio 2020.3 用户

**高兼容性项目**:
1. ✅ ABB_PALLETIZING_TEMPLATE - 完全兼容
2. ✅ RAPID-Scripts-and-Demos - 完全兼容
3. ⚠️ Palletizer-Sorting - 需要检查版本
4. ⚠️ SortingProductionLine - IRB 1200 版本可用

### 项目选择指南

| 您的需求 | 推荐项目 |
|---------|---------|
| 码垛应用开发 | ABB_PALLETIZING_TEMPLATE |
| 学习 RobotStudio 基础 | Palletizer-Sorting + 教程 |
| 多机器人协作 | SortingProductionLine |
| 需要功能模块 | RAPID-Scripts-and-Demos |
| 安全标准实施 | Palletizer-Sorting |

## 测试运行步骤

### 通用步骤

1. **解压/打开项目**
   ```
   对于 .rspag 文件:
   - 在 RobotStudio 中选择 "文件" > "打开"
   - 选择 Pack&Go 文件
   - 按照向导解压
   ```

2. **检查版本兼容性**
   ```
   - 查看项目 README
   - 确认 RobotWare 版本
   - 必要时升级/降级
   ```

3. **加载虚拟控制器**
   ```
   - 启动虚拟控制器
   - 检查 I/O 配置
   - 验证程序模块
   ```

4. **运行测试**
   ```
   - 切换到 "自动" 模式
   - 点击 "播放" 按钮
   - 观察机器人运动
   ```

### 注意事项

⚠️ **安全警告**:
- 首次运行请使用 "手动" 模式
- 检查所有安全区域设置
- 确认工具和工作对象坐标系

⚠️ **版本警告**:
- 不同 RobotWare 版本可能不兼容
- 建议在虚拟环境中测试
- 备份原有项目

## 贡献和反馈

这些项目均为开源项目，请遵守各自的许可证要求。

如果您在使用过程中发现问题或有改进建议，欢迎：
1. 在原项目提交 Issue
2. 向我们的仓库提交反馈
3. 分享您的使用经验

## 许可证

各项目保持其原始许可证：
- ABB_PALLETIZING_TEMPLATE: 请查看项目内 LICENSE 文件
- SortingProductionLine: MIT License
- Palletizer-Sorting: MIT License
- RAPID-Scripts: 请查看项目内 LICENSE 文件

## 更新记录

### 2026-04-21
- ✨ 初始收集和整理
- 📥 下载 4 个开源项目
- 📝 创建项目说明文档

---

**收集者**: [@meisyangb](https://github.com/meisyangb)  
**最后更新**: 2026-04-21  
**用途**: 学习、测试和参考
