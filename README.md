# 🎲 3D Physics Dice Roller (工业级 3D 物理骰子引擎)

> 这是一个基于 WebGL (Three.js) 与 Cannon.js 驱动的纯前端 3D 掷骰子引擎。单文件（Single-file）架构，零打包依赖，开箱即用。完美适用于桌面端跑团（TTRPG）、互动游戏以及**企业游戏化学习管理系统（LMS）**中的随机化任务调度。

**🔗 [点击这里体验在线 Demo](https://WANGGX-Gex.github.io/3d-dice-roller/)**

---

## 💡 核心特性 (Key Features)

本引擎在图形学渲染与物理碰撞上进行了严密的数学重构，解决了传统 Web 3D 骰子常见的穿模、贴图拉伸与物理悬停问题：

* **精确的多面体几何与 UV 映射：**
    * 重构了 **D10 / D100** 的局部坐标系，确保底半球风筝面的数字绝对正向，无镜像、无倒置。
    * 手写了 **D4**（正四面体）的极坐标旋转与顶点阵列映射，实现了实体骰子标准的三点式向心排版。
* **严密的物理引擎容错 (Anti-Stacking & Anti-Penetration)：**
    * **防堆叠机制：** 实时监控静止刚体的 Y 轴高度，一旦检测到骰子“叠罗汉（Cocked Dice）”，自动施加向心微小冲力将其拨落。
    * **倾斜唤醒机制：** 针对硬币（D2）及大面数骰子设置严苛的水平法线点积阈值（0.95），彻底消除物理引擎中的倾斜休眠（Sleep）Bug。
* **原生级移动端适配 (Native-App UX)：**
    * **动态 FOV：** 移动端自动拉远摄像机透视矩阵，确保骰盘完整居中。
    * **弹性重排 (Flex Order)：** 移动端采用 Bottom Sheet（底部滑动抽屉）式选单与手风琴折叠式结果页，保证核心视野不被遮挡。
* **数据驱动的状态机 (State Machine)：**
    * 抛弃繁杂的 DOM 操作，采用类似 React 的单向数据流管理 UI 状态，自动计算骰子上限（Max: 30）并联动按钮置灰。

## 🛠 技术栈 (Tech Stack)

* **HTML5 / CSS3 / Vanilla JavaScript** (纯原生代码，无框架耦合)
* **[Three.js (r128)](https://threejs.org/)** - 3D 渲染与场景构建
* **[Cannon.js (0.6.2)](https://schteppe.github.io/cannon.js/)** - 刚体物理引擎碰撞计算

## 🚀 快速开始 (Usage)

本项目采用极致的单文件极客架构。

1. 克隆或下载本仓库。
2. 直接在任意现代浏览器（Chrome, Edge, Safari）中双击打开 `index.html`。
3. Enjoy! 无需 `npm install`，无需构建工具。

*如需集成到现有的 React/Vue 工程中，可直接将其作为 `<iframe src="index.html">` 嵌入，或通过 `postMessage` 与父级 LMS 系统进行结算数据的通讯。*

## 👨‍💻 制作名单 (Credits)

* **Designed & Engineered by:** [@WANGGX](https://github.com/WANGGX-Gex)
* **Special Thanks:** 感谢好友 **@fonk** 与 **@bhonny** 在项目开发过程中提供的无私技术辅导与情绪支持！

## 📄 开源协议 (License)

[MIT License](LICENSE)
