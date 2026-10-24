# MTR Next Rail

**为 YMTR 3.x 提供 MTR 4.x 风格的精确曲线轨道预览** —— 独立版，只做预览。

[![Minecraft](https://img.shields.io/badge/Minecraft-1.20.1-green)](https://minecraft.net)
[![Fabric](https://img.shields.io/badge/Loader-Fabric-blue)](https://fabricmc.net)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

---

## 这是什么

YMTR（MTR 3.6.4.2 分支）的轨道预览是把一堆短线段拼起来，弯道上会「抖」。这个模组把 MTR 4.0 的**样条曲线预览**搬了过来：预览线和最终铺出来的轨道**完全重合**，弯道平滑。

> 本模组是 [MTR Next](https://github.com/szkele1145/mtr-next) 的**轨道预览拆分版**。原项目还包含 4.0 车包加载、自定义编组、bbmodel 渲染等功能；当前拆分版**只保留轨道预览**，因为它是最稳定、最独立的一块。

## 功能

| 功能 | 说明 |
|---|---|
| **精确曲线预览** | 用 MTR 4.0 的样条算法，预览线与实铺轨道逐点重合 |
| **数据面板** | 实时显示 长度 / 坡度 / 方位角 / XYZ 偏移 |
| **严格触发条件** | 只在「手持轨道连接器 + 已选一号节点 + 准心 5 格内另一个节点」时显示，其余情况完全不出现 |
| **几何护栏** | 两点之间若构不出合理曲线（长度超过直线 4 倍 + 6 格），宁可不画也不画一条横跨半空的怪线 |

## 用法

1. 手持**轨道连接器**（MTR 的连接器物品）
2. 用准心对准一个**轨道节点方块**并点击（选定一号节点）
3. 把准心移到 5 格内另一个轨道节点方块上

屏幕上会出现：

- 一条**白色双钢轨**预览线，形状与实际会铺出的轨道完全一致
- 一个数据面板：

```
长度   12.34 格
坡度   +2.50%  (+1.43°)
方位   45.0°
偏移   X +3.2  Z -1.8
```

4. 再点一下完成连接

> **不显示**的情况：空手、没选一号节点、准心没指向方块、超出 5 格、两点之间已有真实轨道。

## 兼容性

| 项目 | 版本 |
|---|---|
| Minecraft | 1.20.1 |
| Fabric Loader | ≥ 0.15.6 |
| Fabric API | 任意 1.20.1 版本 |
| **MTR** | **YMTR（MTR 3.6.4.2 分支）必需** |
| Java | 17+ |

**必需依赖**：本模组不能独立运行，必须装 MTR（YMTR 版）。不兼容原版 MTR 3.2.x。

## 安装

1. 安装 Fabric Loader 与 Fabric API
2. 安装某 MTR（YMTR）3.6.4.2 分支
3. 把 `mtr-next-rail-*.jar` 放进 `mods/`
4. 启动游戏

## 从源码构建

```bash
# Windows（JDK 17 必需）
set GRADLE_USER_HOME=C:\gradle-home
gradlew.bat build

# 产物：build/libs/mtr-next-rail-<version>-1.20.1-fabric.jar
```

## 已知限制

- **只做预览**：不含 4.0 车包加载、自定义编组、bbmodel 渲染
- 依赖 YMTR 的内部方法（`RenderTrains.renderRailStandardSafe`、`Rail.render`），若 YMTR 大改版可能失效

## 致谢

- [MTR](https://github.com/jonafanho/Minecraft-Transit-Railway) —— 轨道渲染与曲线算法
- [YMTR](https://github.com/) 3.6.4.2 分支 —— 提供 3.x 宿主环境

## 许可

MIT