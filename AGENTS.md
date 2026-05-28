# AGENTS.md — Framer Theme (发布版)

> 用于发布到 Obsidian 社区主题商店的仓库操作手册。

---

## 1. 仓库结构

提交到 GitHub 的主题仓库应包含以下文件：

```
Framer/
├── theme.css          # 主题样式（核心文件）
├── manifest.json      # 主题元数据
├── README.md          # 社区商店展示文档（必须！）
├── screenshot.png     # 主题预览图（必须！1280×720 推荐）
├── LICENSE            # 开源许可证（推荐 MIT）
└── AGENTS.md          # 本文件（可选，不显示在商店中）
```

### 1.1 manifest.json 规范

当前内容：

```json
{
  "name": "Framer",
  "version": "1.1.0",
  "minAppVersion": "1.0.0",
  "author": "TheViviana",
  "authorUrl": "https://github.com/TheViviana"
}
```

**版本发布前需更新：**
- `version` — 遵循语义化版本（`major.minor.patch`）
- `minAppVersion` — 测试兼容的最低 Obsidian 版本
- `authorUrl` — 你的个人主页或 GitHub 链接

### 1.2 README.md 必备内容

社区商店会渲染仓库的 `README.md`，至少包含：

- 主题名称与简介
- 截图（建议 2-3 张：编辑器、阅读模式、设置面板）
- 安装方式（BRAT / 手动）
- 功能特性列表
- Accent 颜色切换说明（Pink / Cyan / Purple）
- Style Settings 说明
- 插件兼容性（Dataview、Kanban、Calendar）
- 致谢 / 许可证

---

## 2. 发布工作流

### 2.1 首次提交到社区商店

1. 在 GitHub 创建仓库，命名为 `Obsidian-Theme-Framer`
2. 推送 `theme.css`、`manifest.json`、`README.md`、`screenshot.png` 到 `main` 分支
3. 创建 GitHub Release，Tag 名与 `manifest.json` 中 `version` 一致
4. 到 [obsidian-releases](https://github.com/obsidianmd/obsidian-releases) 提交 PR，在 `community-themes.json` 中添加条目：

```json
{
  "name": "Framer",
  "author": "TheViviana",
  "description": "A clean dark theme with Pink Accent System, inspired by Framer's design system",
  "repo": "TheViviana/Obsidian-Theme-Framer",
  "screenshot": "screenshot.png",
  "branch": "main"
}
```

### 2.2 版本更新流程

```
1. 修改 theme.css（完成变更）
2. 更新 manifest.json 中 version（如 "1.2.0"）
3. 如有必要更新 minAppVersion
4. 更新 README.md 变更日志
5. 更新 AGENTS.md 中的架构速查行号
6. git commit -m "chore: bump to 1.2.0"
7. git tag 1.2.0
8. git push && git push --tags
9. GitHub 自动发布 Release（如已配置 Actions）
```

### 2.3 推荐 GitHub Actions 工作流

创建 `.github/workflows/release.yml`：

```yaml
name: Release
on:
  push:
    tags: ["*"]
jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Create Release
        uses: softprops/action-gh-release@v2
        with:
          files: |
            theme.css
            manifest.json
          generate_release_notes: true
```

---

## 3. 发布前检查清单

### 3.1 样式检查

- [ ] `theme.css` 在 Obsidian 中加载正常，无白屏或样式断裂
- [ ] 深色主题下所有 UI 元素可见（按钮、输入框、下拉菜单等）
- [ ] 浅色主题下所有 UI 元素可见
- [ ] 切换 `accent-cyan` / `accent-purple` 后 hover 色跟随变化
- [ ] `.framer-heading-gradient` 开关可控制标题颜色
- [ ] 标签页切换无白色边框闪烁
- [ ] 阅读模式 / 实时预览 / 源码模式均正常
- [ ] 移动端 `.framer-mobile` 样式生效
- [ ] 插件兼容：Dataview 表格、Kanban 看板、Calendar 日历

### 3.2 代码检查

- [ ] 品牌交互色使用 `var(--color-brand)` 或 `rgba(255, 143, 184, ...)` 粉色系
- [ ] 无硬编码 `border-radius: 4px`（应使用 `var(--radius-s)`）
- [ ] 无未使用的 CSS 变量
- [ ] `@settings` 块中的每个 `id` 在 CSS 中有对应规则
- [ ] 所有 `body.framer-*` 类在 `@settings` 中有对应条目

### 3.3 截图准备

- [ ] 分辨率 1280×720 或 1920×1080
- [ ] 展示编辑器界面（带代码、表格、标签页）
- [ ] 展示阅读模式
- [ ] 展示设置面板（Style Settings）
- [ ] 文件大小 < 1MB

---

## 4. CSS 架构速查

### 4.1 代码组织（theme.css 内）

| 区域 | 行号 | 说明 |
|------|------|------|
| `@settings` | L1–236 | Style Settings 注释块 |
| `.theme-dark` | L238–507 | 深色模式所有 CSS 变量（Pink Accent System） |
| `.theme-light` | L509–779 | 浅色模式所有 CSS 变量（Pink Accent System） |
| 标题色开关 | L781–790 | `body:not(.framer-heading-gradient)` 重置 |
| 基础样式 | L792–813 | body 变量、过渡规则、圆角、间距 |
| 排版 | L838–902 | 标题字号、行高、编辑器字体 |
| 功能开关 | L904– | body.framer-* 类控制的特性 |
| 组件 | L1078– | 代码、表格、标注、按钮、输入 |
| 编辑器 | L1351– | CM6 活动行、Canvas |
| 插件 | L2106– | Dataview、Kanban、Calendar、Excalidraw |
| 移动端 | L2246– | is-mobile 适配 |
| Accent 变体 | L2325– | Cyan / Purple 变体 |
| Snippets | L2579– | Bold Pink、Immersive Translate、Minimal Tables、Floating Status Bar |
| 双链高亮 | L2648– | Internal Links |

### 4.2 色彩系统

#### Pink Accent System（默认）

品牌色 `--color-brand: #FF8FB8`，包含 6 个粉色变量：

| 变量 | 深色值 | 用途 |
|------|--------|------|
| `--color-brand` | `#FF8FB8` | 主品牌色 |
| `--color-pink-soft` | `#FFC1D6` | 柔和粉（标签、标签页指示器） |
| `--color-pink-rose` | `#F29BB7` | 玫瑰粉（渐变、标题） |
| `--color-pink-dusty` | `#D48CA2` | 暗粉（代码属性） |
| `--color-pink-lavender` | `#D5B4FF` | 薰衣草紫（列表标记、代码函数） |
| `--color-hot` | `#FF5FA2` | 热粉（重要标记、Graph tag） |

#### Accent 变体

- `body.accent-cyan`：`--color-brand: #00BCD4`
- `body.accent-purple`：`--color-brand: #BB86FC`

### 4.3 变量规范

- 品牌交互色使用 `rgba(255, 143, 184, ...)` 或 `var(--color-brand)`
- 圆角使用 `var(--radius-s)` / `var(--radius-m)` / `var(--radius-l)` / `var(--radius-xl)`
- 过渡使用 `var(--transition-default)`（150ms ease-out）

### 4.4 类名约定

- 功能开关：`body.framer-{name}`（如 `.framer-tabs`）
- Accent 变体：`body.accent-{color}`（如 `body.accent-cyan`）
- 不使用时：`body.framer-{name}-off` 配合 `:not()` 选择器

---

## 5. 版本历史记录规范

每次版本更新需在 `theme.css` 顶部注释块中记录：

```
## v1.1.0 (2026-05-29)
- 重构品牌色系统：从 Blue Accent 迁移到 Pink Accent System
- 新增完整的 Light Mode（.theme-light）支持
- 新增 Pink Accent System（6 个粉色变量 + 粉色系 hover/交互色）
- 新增浅色模式下的完整变量定义
- 标题色系从蓝色渐变改为粉紫渐变
- 代码高亮从蓝色系改为粉色系
- 链接色从蓝色改为粉色 (#FF75AC)
- 灰阶从纯灰改为紫灰调 (#6F6870 / #9B9098)
- 背景色从纯黑灰改为偏紫调 (#111114 / #0B0B0D)
- 保留 Accent 变体（Cyan / Purple）
- 文件行数从 2290 行增加到 2658 行
```

同时更新 README.md 底部的变更日志。

---

## 6. 故障排查

| 问题 | 原因 | 解决 |
|------|------|------|
| 主题商店看不到主题 | 未提交 PR 到 obsidian-releases | 按 2.1 流程提交 |
| 主题不生效 | manifest.json 格式错误 | 检查 JSON 语法 |
| 设置开关无效 | `@settings` 中 id 与 CSS 不匹配 | 确保 ID 一致 |
| 插件样式不显示 | 类名未加 `body.framer-*` 前缀 | 按规范加上 |
| 浅色模式异常 | `.theme-light` 变量缺失 | 检查浅色变量是否完整 |
| 粉色不显示 | 旧版缓存 | 清除 Obsidian 缓存后重启 |
