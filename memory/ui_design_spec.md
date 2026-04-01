# UI 视觉规范核心速查表（完整版）
> 来源：用户视觉规范文档 v1.0（全量提取）
> 适用：Stitch / Cursor / Trae / Figma Make / Copilot 等 AI 生成 UI

## ⚠️ 使用层级说明

| 场景 | 加载内容 |
|------|---------|
| 生成**基础 UI 界面**（默认） | 第一章～第九章（静态规范，不含动效） |
| 生成**前端交互稿**（用户明确说"交互稿"/"需要动效"/"前端实现"） | 全部章节，追加第八章动效规范 |

---

## 一、色彩系统

### 主色
- 品牌蓝：`#165DFF`
- **每页不超过 3 处**，仅用于：主要 CTA 按钮、当前选中状态、强调链接
- 禁止用于：背景、卡片底色、图标默认色、装饰

### 语义色（功能色）
| 用途 | 颜色 | Hex |
|------|------|-----|
| 主色/信息 | 蓝 | `#165DFF` |
| 危险/错误 | 红 | `#F53F3F` |
| 警告 | 橙 | `#FF7D00` |
| 成功 | 绿 | `#00B42A` |
| 特殊/高亮 | 紫 | `#722ED1` |

### 背景色 Token（双主题）
| Token | 浅色 | 深色 | 用途 |
|-------|------|------|------|
| `bg_page_1` | `#FFFFFF` | `#17181A` | 主页面背景 |
| `bg_page_2` | `#F2F3F5` | `#212224` | 侧边栏/次级背景 |
| `bg_card_1` | `#FFFFFF` | `rgba(235,241,255,0.05)` | 普通卡片 |
| `bg_card_2` | `#F2F3F5` | `rgba(235,241,255,0.05)` | 次级卡片/列表行 |
| `bg_card_3` | `#FFFFFF` | `#2E2E32` | 弹窗/抽屉 |

### 文字色 Token
| Token | 浅色 | 深色 | 用途 |
|-------|------|------|------|
| `color_text_1` | `#0E1524` | `#FFFFFF` | 一级文字（标题、主内容） |
| `color_text_2` | `#32353D` | `rgba(255,255,255,0.80)` | 二级文字（副标题、说明） |
| `color_text_3` | `#959BA6` | `rgba(255,255,255,0.32)` | 三级文字（占位符、辅助说明） |
| `color_text_4` | `#BFC2C7` | `rgba(255,255,255,0.16)` | 四级文字（禁用状态） |

### 图标色 Token
| Token | 浅色 | 深色 | 用途 |
|-------|------|------|------|
| `color_icon_1` | `#535966` | `rgba(255,255,255,0.80)` | 主要图标（强调/选中） |
| `color_icon_2` | `#737780` | `rgba(255,255,255,0.32)` | **默认图标**（大多数场景） |
| `color_icon_3` | `#BFC2C7` | `rgba(255,255,255,0.16)` | 辅助图标 |

### 边框色 Token
| Token | 浅色 | 深色 | 用途 |
|-------|------|------|------|
| `color_border_1` | `rgba(25,29,36,0.08)` | `rgba(247,250,255,0.06)` | 列表分割线 |
| `color_border_2` | `rgba(25,29,36,0.12)` | `rgba(247,250,255,0.16)` | **卡片边框** |
| `color_border_3` | `rgba(25,29,36,0.20)` | `rgba(247,250,255,0.24)` | 输入框/按钮边框 |
| `color_border_4` | `rgba(25,29,36,0.32)` | `rgba(247,250,255,0.48)` | 选中/focus 边框 |

### 交互叠加层 Token（hover/active 用）
| Token | 值 | 用途 |
|-------|-----|------|
| `interaction_weak` | `rgba(24,30,41,0.05)` | 列表行 hover |
| `interaction_medium` | `rgba(24,30,41,0.08)` | 卡片/按钮 hover |
| `interaction_strong` | `rgba(24,30,41,0.16)` | 主要操作 hover |

### 功能色背景
| 状态 | 背景色 |
|------|--------|
| 成功 | `rgba(0,180,42,0.08)` |
| 警告 | `rgba(255,125,0,0.08)` |
| 错误 | `rgba(245,63,63,0.08)` |
| 信息 | `rgba(22,93,255,0.08)` |

### CSS 实现方式
```css
:root { /* 浅色默认 */ }
[data-theme="dark"] { /* 深色覆盖 */ }
```

---

## 二、字体排版

### 字体栈
```css
/* 中英文混排（默认） */
font-family: "PingFang SC", "Noto Sans SC", "Microsoft YaHei",
             -apple-system, BlinkMacSystemFont, "Segoe UI", Inter, sans-serif;
/* 代码 */
font-family: "JetBrains Mono", "Fira Code", Consolas, monospace;
```

### 字号阶梯（基准 14px，跳跃式）
| 用途 | 字号 | 字重 | 行高 |
|------|------|------|------|
| Hero 大标题 | 36px | 500 | 1.3 |
| 页面一级标题 | 28px | 500 | 1.4 |
| 卡片/模块标题 ★ | 18px | 500 | 1.5 |
| 列表/表格标题 | 16px | 500 | 1.5 |
| 正文（默认★） | 14px | 400 | 1.6 |
| 辅助说明 | 13px | 400 | 1.6 |
| 时间/标注 | 12px | 400 | 1.5 |
| 标签/按钮文字 | 12px | 500 | 1.4 |
| 代码 | 13px | 400 | 1.7 |

### 字重规则
- **只用 400 / 500**，禁止 600 / 700 / bold
- 跳跃式层级：28 → 18 → 14 → 12，**禁止加 15/17/20/22px 中间值**
- 数字统计用 `font-variant-numeric: tabular-nums`

### 特殊场景
- 数据大卡片的核心数字：可用 32px 或 40px，形成强烈对比
- H2 模块标题：18px，不要 20px 或 22px（差 2px 不够突出）
- 每页字号种类不超过 3 种（加辅助说明 12px 最多 4 种）

---

## 三、间距系统（基准 4px）

| Token | 值 | 典型用途 |
|-------|-----|---------|
| space-2 | 4px | icon 与文字间距 |
| space-3 | 8px ★ | 列表项间距、行内元素 |
| space-5 | 16px ★ | 卡片内边距、按钮水平内边距、模块间距 |
| space-7 | 24px ★ | 标准卡片/面板内边距、弹窗内边距 |
| space-8 | 32px | 模块与模块间距、章节分割 |
| space-9 | 48px | 页面级间距、Hero 区域 |

### 页面布局间距（重要）
- 卡片内边距：**24px**（固定，不随屏幕变化）
- 卡片与卡片间距：**16px**
- 模块与模块间距：**32px**（不要 24px，否则模块间没有呼吸感）
- 页面外边距（桌面）：24~32px
- 导航栏高度：**52px**（默认中，留足信息空间）
- 侧边栏内边距：**24px**，导航路径缩进 **8px** 递增
- 禁止使用非 4 倍数间距（5px/7px/11px/15px）

---

## 四、圆角系统

| 组件 | 圆角 | Token |
|------|------|-------|
| 按钮（默认） | 6px | radius-md |
| 按钮（胶囊型） | 9999px | radius-full |
| 输入框/选择框 | 6px | radius-md |
| 卡片 ★ | 8px | radius-lg |
| 弹窗 Modal | 12px | radius-xl |
| 抽屉 Drawer | 0px | radius-none（靠边贴屏） |
| 下拉菜单 | 8px | radius-lg |
| Tag/Badge | 4px | radius-sm |
| Tooltip | 6px | radius-md |
| 头像（圆形） | 9999px | radius-full |
| 进度条 | 9999px | radius-full |
| 表格（外框） | 8px | 内部行无圆角 |

---

## 五、阴影系统

### 原则：边框 vs 阴影二选一
- **浅色模式**：用细边框（`1px solid color_border_2`）区分卡片层级，不加阴影
- **深色模式**：用背景色差区分层级，边框和阴影都省略
- 阴影只用于真正需要浮层感的元素（下拉菜单、Tooltip、弹窗）

| 组件 | 默认阴影 | hover阴影 |
|------|---------|---------|
| 卡片（可交互） | shadow-sm | shadow-md |
| 下拉菜单/Tooltip | shadow-md | — |
| 弹窗 Modal | shadow-lg | — |
| 抽屉 Drawer | shadow-xl | — |
| 按钮 | **无** | **无** |
| 输入框 | 无 | shadow-xs（focus） |
| 导航栏（fixed） | shadow-sm | — |

### 深色模式阴影替代
```css
[data-theme="dark"] {
  --shadow-sm: 0 0 0 1px var(--color-border-2);
  --shadow-md: 0 4px 16px rgba(0,0,0,0.40), 0 0 0 1px var(--color-border-1);
}
```

---

## 六、组件尺寸

### 控件高度（统一基准）
| 尺寸 | 高度 | 用途 |
|------|------|------|
| xs | 22px | Mini 按钮、紧凑 Tag |
| sm | 26px | Small 按钮 |
| md ★ | 32px | 默认按钮、输入框、选择框 |
| lg | 40px | Large 按钮/输入框 |
| xl | 48px | Hero 区域特大按钮 |

### 图标尺寸
- 行内图标（配 14px 文字）：**16px**（最常用）
- 导航图标：**20px**
- 空状态图标：**48~64px**
- 功能大卡片图标：32~40px
- 禁止图标超过 20px 用于行内（除非是大卡片）

---

## 七、Hover 交互规范

### 原则：克制，只加叠加层
- 列表行 hover：加 `interaction_weak`（5% 透明叠加），不改变文字颜色、不改变边框、不位移
- 卡片 hover（可点击）：加 `interaction_medium`（8%），边框从 `border_2` 升为 `border_3`
- 按钮 hover：加 `interaction_medium`，颜色通过 CSS 变量自动切换
- **禁止** hover 时元素位移（`translateY(-2px)` 等）
- 动画时间：**150ms ease-out**，不要 300ms（太慢显迟钝）
- 禁止循环动画、呼吸灯、闪烁效果（除明确的加载状态）

---

## 八、动效规范

### 时间 Token
| Token | 值 | 用途 |
|-------|-----|------|
| `--dur-fast` | 150ms | hover、tooltip、focus、箭头旋转 |
| `--dur-normal` | 300ms | 弹窗、抽屉、展开、Toast |
| `--dur-slow` | 450ms | 页面级路由切换、骨架屏 |
| `--delay-tooltip` | 100ms | Tooltip 出现延迟 |

### 缓动 Token
| Token | 曲线 | 用途 |
|-------|------|------|
| `--ease-enter` | `cubic-bezier(0.3,0,0.6,1)` | 进入动画 |
| `--ease-exit` | `cubic-bezier(0.3,0,0.6,1)` | 退出动画 |
| `--ease-spring` | `cubic-bezier(0.34,1.56,0.64,1)` | Toast、成功态弹跳 |

### 常用组件动效速查
| 组件 | 时间 | 缓动 | 说明 |
|------|------|------|------|
| 按钮 hover | dur-fast | ease-enter | 背景色变化 8% 透明度 |
| 按钮 active | 50ms（直接写） | ease-enter | scale(0.97) 模拟物理按压 |
| 按钮成功态 | 200ms | ease-spring | spinner→✓，1.8s 后恢复 |
| 输入框 focus | dur-fast | ease-enter | border-color + box-shadow 同时变化 |
| 下拉展开 | dur-fast | ease-enter | translateY(-6px)+scaleY(0.82)→正常 |
| 下拉收起 | 100ms（直接写） | ease-exit | 无延迟 |
| 弹窗进入 | dur-normal | ease-enter | scale(0.2)+opacity(0)→正常，同时开始 |
| 弹窗退出 | 200ms | ease-exit | 比进入快 100ms |
| 弹窗归位动画 | 400ms | cubic-bezier(0.3,0,0.6,1) | translate 写在 scale 前，透明度 offset 0.75 开始消失 |
| 抽屉进入 | dur-normal | ease-enter | translateX(100%)→0 |
| 抽屉退出 | 250ms | ease-exit | 比进入快 50ms |
| 折叠展开 | dur-normal | ease-enter | max-height JS 动态取 scrollHeight |
| 折叠收起 | 250ms | ease-exit | 先固定高度，rAF 后设为 0 |
| Tab 指示线 | dur-normal | ease-enter | left + width 同时 transition |
| 列表插入 | dur-normal | ease-enter | 列表项 absolute 让内容滑入，其他项移位 |
| 列表删除 | 240ms | ease-exit | 先缩小高度，然后位移补位 |
| Toast 进入 | dur-normal | ease-spring | translateX(100%)→0，spring 弹入 |
| Toast 退出 | 240ms | ease-exit | 先淡出+缩小，再 max-height 收起 |
| 菜单折叠 | dur-normal | ease-enter | 220px→56px，根据内容宽度动态 |

### 动效禁止清单
- `transition: all`（用具体属性）
- hover 时 `translateY` / `scale` 上浮放大
- 退出时间 > 进入时间
- 无限循环动画（除 loading）
- 退出直接 `display:none`（等 transitionend）
- 用 `top` / `left` / `margin` 做位移（用 transform）
- SVG 箭头用 inline style 加 transition（用 CSS class）

---

## 九、页面结构与视觉焦点

### 每页必须有一个视觉焦点
- 明确告知 AI：「本页视觉焦点是 [具体说明什么]」
- 其他元素都要为焦点让路

### 典型布局规范
- 页面顶部 Page Header：标题 28px，副标题 14px `color_text_3`，间距 4px，标题不要加颜色
- 数据统计卡片：核心数字 **32px 加粗**，标签 **12px** `color_text_3`，字号比约 2.7 倍，形成强烈对比
- 表格：表头 `color_text_2` 12px，内容 `color_text_1` 14px，表头和内容有明显对比
- 空状态页面：图标 48px，标题 16px，说明 14px `color_text_3`，CTA 按钮（空状态转化时，是页面唯一彩色元素）

---

## 十、深色模式规范

- 背景色：`#17181A`（不是 `#000000` 也不是 `#1a1a1a`）
- 卡片背景：`rgba(235,241,255,0.05)`（微蓝透明，自然融入）
- 层级区分：靠背景色差（`#17181A` / `#212224` / `#28282B`），不用边框和阴影
- 边框：`color_border_1`（6% 白色透明），只在需要分割的地方用
- 文字层级：100% / 80% / 32% / 16% 白色透明度递减
- 功能色（成功/警告/错误）保持不变，只是背景透明度从 8% 升到 10%
- 深色模式禁止使用 `box-shadow`（几乎不可见，改用边框替代）

---

## 十一、AI 生成 UI 的 System Prompt 模板

```
你是一个 SaaS 后台管理系统的 UI 工程师。

视觉规范如下，严格遵守，不要自由发挥：

1. 字号只用 28/18/14/12px 的跳跃式层级，禁止中间值
2. 主色 #165DFF 在当前页面出现不超过 3 处，只用于最重要的操作
3. 卡片内边距 24px，模块间距 32px，卡片间距 16px
4. 卡片只用细边框（1px, rgba(25,29,36,0.12)），不加阴影
5. 图标默认用次要色（#737780），只有选中/强调才用高对比度
6. Hover 只叠加 5% 透明层，不改变文字颜色、不位移元素
7. 动画时间 150ms ease-out，弹窗 300ms

本页视觉焦点是：[在此填写]
所有元素都要为焦点让路，其余元素保持克制。

CSS 变量来源：design-tokens.ts / 色彩设计规范_Color-Design-Spec.md
```

---

## 十二、5 秒自检清单

1. 扫一眼页面，能在 2 秒内找到最重要的操作吗？→ 视觉焦点是否清晰
2. 数一下彩色元素，超过 3 个？→ 主色是否滥用
3. 卡片有阴影吗？→ 删除阴影，改用细边框
4. 字号有中间值吗？→ 合并中间层级
5. 内边距是多少？→ 小于 20px 太拥挤，改为 24px
