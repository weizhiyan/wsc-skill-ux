# wsc-ux

> 专业的 UI 设计提示词生成与交互需求深度优化专家。

将模糊的产品想法转化为像素级精准的 UI 设计描述。无论是为 Figma Make/Stitch 生成设计指令，还是梳理复杂的系统交互逻辑，wsc-ux 都能提供工业级的专业输出。

---

## 🎨 WSC 系列成员

- **[wsc-skill-image](https://github.com/weizhiyan/wsc-image)** — AI 视觉创意专家
- **[wsc-skill-ux](https://github.com/weizhiyan/wsc-idea)** — UI/UX 设计与需求专家

---

## 核心能力

### 1. 交互需求深度优化 (UX Refinement)
- **口语转规格**：将「点击这个按钮跳出菜单」转化为包含动效曲线 (Easing)、触发延迟 (Latency) 和反馈强度 (Feedback) 的专业规格说明。
- **状态全覆盖**：自动补全 Default, Hover, Active, Disabled, Loading, Error 等所有交互状态。
- **逻辑梳理**：识别业务逻辑中的歧义，通过弹窗引导用户确认最优路径。

### 2. UI 界面提示词生成 (UI Prompting)
- **Make / Stitch 优化**：针对 Figma AI 插件深度优化，生成的提示词包含明确的布局容器 (Autolayout)、间距配置 (Spacing) 和原子化组件拆解。
- **信息层级设计**：自动规划页面的视觉重心，平衡功能性与美学。
- **模拟真实数据**：在提示词中预填符合场景的真实占位数据，而非简单的 Lorem Ipsum。

### 3. 智能引导系统
- **动态弹窗**：当描述不全时，自动弹出包含「配色方案」、「圆角风格」、「字体偏好」等维度的选择题。
- **设计风格迁移**：支持通过参考图提取 UI 规范，并应用到新功能设计中。

---

## 运行架构

### 1. 需求解析阶段
识别用户输入的是“视觉设计需求”还是“逻辑梳理需求”。
- **视觉需求**：走 UI Prompting 流程。
- **逻辑需求**：走 UX Specification 流程。

### 2. 专业参数介入
引入 HSBA 色彩模型、Bézier 动效参数、原子化设计原则 (Atomic Design) 进行增强。

### 3. 结构化输出
输出分为：场景目标、模块拆解、状态逻辑、Make/Stitch 专用代码块。

---

## 文件结构

```
wsc-ux/
├── SKILL.md                    # 核心 Skill 文件，定义 UX 规则
├── README.md                   # 本文档
├── templates/
│   └── ui_design.md            # UI 设计输出模板
└── memory/
    ├── ui_prompts.md           # 视觉风格经验库
    ├── interaction_refine.md   # 交互参数习惯
    └── ui_design_spec.md       # 基础设计规格规范
```

---

## 版本历史

- **v3.2** — 2026-04-14：重构为 WSC 系列成员。全面升级交互优化逻辑，支持 Make/Stitch 深度适配。
- **v3.0** — 2026-04-02：从 wsc-idea 进化，专注 UX 领域。
