# wsc-skill-ux — AI UI/UX 专家

[![Claude Code](https://img.shields.io/badge/Claude-Code-black?logo=anthropic)](https://claude.ai/code)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> 将模糊的产品想法，转化为像素级精准的 UI 设计描述。

不管是为 Figma Make/Stitch 生成设计指令，还是梳理复杂的系统交互逻辑，wsc-ux 都能提供工业级的专业输出。

---

## 🎯 核心能力

wsc-ux 通过两个核心阶段，将你的口语需求转化为生产级方案：

### Part A. 交互需求深度优化 (UX Refinement)
- **口语转规格**：将「点击按钮跳出菜单」转化为包含动效曲线 (Easing) 和触发延迟的专业说明。
- **状态全覆盖**：自动补全 Hover, Active, Loading, Error 等所有关键交互状态。
- **边界条件梳理**：识别逻辑歧义，通过弹窗引导你确认最优路径。

### Part B. UI 界面提示词生成 (UI Prompting)
- **Make / Stitch 深度优化**：生成的提示词包含明确的布局容器 (Autolayout)、原子化组件和真实占位数据。
- **内置视觉规范**：自动应用基于 8px 栅格系统的专业间距、颜色体系和圆角标准。
- **风格迁移**：支持从参考图提取 UI 规范，并直接应用到新功能设计中。

---

## 🚀 三大应用场景

| 场景 | 触发方式 | 输出结果 |
| :--- | :--- | :--- |
| **1. 碎片梳理** | 发送零碎想法、动画或布局描述 | 结构化交互/动效规格文档 |
| **2. 提示词补全** | 给出粗糙结构，说「帮我补充细节」 | 完整的 Make/Stitch 系统提示词 |
| **3. 产品顾问** | 说「帮我分析」「评审一下现有流程」 | 触发顾问模式选择 (A~F) 并深度分析 |

---

## 🛠️ 怎么使用

### 1. 安装 (Claude Code)
将 `wsc-ux` 文件夹放入你的技能目录：
```bash
~/.claude/skills/wsc-ux/
```

### 2. 触发
直接说出你的设计想法或痛点，AI 会自动识别场景并按规格输出。

### 3. 协作
生成的交互规格可直接交由 `wsc-ui-builder` 实现，设计的 UI 提示词可直接粘贴进 Figma AI 插件。

---

## 🎨 WSC Creative Suite 系列

- **[wsc-skill-image](https://github.com/weizhiyan/wsc-skill-image)** — AI 视觉创意专家
- **[wsc-skill-ux](https://github.com/weizhiyan/wsc-idea)** — UI/UX 设计与需求专家（当前）

---

> **Design with logic, refine with beauty.**
> —— *WSC Creative Suite*
