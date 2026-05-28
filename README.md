# Framer Theme

> 一款受 Framer 设计系统启发的 Obsidian 主题，Pink Accent System + 完整浅色模式支持。

![screenshot](https://raw.githubusercontent.com/TheViviana/Obsidian-Theme-Framer/main/screenshot.png)

## 特性

- 🌸 **Pink Accent System** — 6 色粉色变量体系，品牌色 `#FF8FB8`
- 🌗 **深色 + 浅色模式** — 完整双主题支持，紫灰调深色 / 暖白浅色
- 🎨 **三种强调色** — 粉色（默认）/ 活力青 / 紫色，一键切换
- 🖼️ **Framer 设计语言** — 极简底色，280px 属性面板，紧凑 UI
- ⚡ **流畅过渡** — 统一的 150ms 平滑动画
- 📱 **移动端适配** — 44px 触摸目标，优化侧边栏
- 🔌 **插件兼容** — Dataview、Kanban、Calendar、Excalidraw

## 安装

### Obsidian 社区商店（推荐）

1. 打开 Obsidian → 设置 → 外观 → 主题
2. 点击「管理」→ 浏览社区主题
3. 搜索 **Framer** → 点击「安装」

### 手动安装（BRAT）

1. 安装 [BRAT](obsidian://show-plugin?id=BRAT) 插件
2. 添加主题仓库：`TheViviana/Obsidian-Theme-Framer`
3. 刷新主题列表并选择 Framer

### 手动下载

1. 下载 [最新 Release](https://github.com/TheViviana/Obsidian-Theme-Framer/releases)
2. 解压到 `.obsidian/themes/Framer/`
3. 重新加载主题

## 使用方法

### 强调色切换

需要安装 [Style Settings](obsidian://show-plugin?id=obsidian-style-settings) 插件：

1. 设置 → Style Settings → Framer Theme → Appearance
2. Accent Style → 选择 Classic Pink / Vibrant Cyan / Purple

### 内置功能开关

| 功能 | 默认 | 说明 |
|------|------|------|
| Framed Tab Headers | 开启 | 标签页边框样式 |
| Section Highlights | 开启 | 设置侧栏高亮 |
| Quick Actions Style | 开启 | 命令面板 Framer 风格 |
| Heading Blue | 开启 | 标题粉色渐变（关闭恢复白色） |
| Reading Mode Prose | 开启 | 阅读模式优化 |
| Canvas Grid | 开启 | 编辑器网格背景 |
| 280px Property Panel | 开启 | 右侧面板固定宽度 |
| Compact 4px Spacing | 关闭 | 更紧凑的间距 |
| Frame Selection Outlines | 开启 | 选中元素蓝色边框 |
| Drag Insertion Indicator | 开启 | 拖拽蓝色指示线 |
| Component Search | 开启 | 文件搜索 Framer 风格 |
| Property Panel Groups | 开启 | 元数据分组样式 |
| Backlinks Connection Panel | 开启 | 反向链接面板样式 |
| Tags as Chips | 开启 | 标签芯片样式 |
| Code Panel Line Numbers | 开启 | 代码行号 Framer 风格 |

### 内置 CSS Snippets

以下样式默认启用，无需额外安装：

- **Bold Pink** — 加粗文字显示为粉色 `#FF69B4`
- **Immersive Translate Red** — 翻译结果显示红色渐变
- **Minimal Tables** — 表格自动撑满、简洁边框
- **Floating Status Bar** — 状态栏悬停滑入

如需关闭，需删除 `theme.css` 末尾对应的 CSS 块。

## 色彩系统

### Pink Accent System（默认）

| 变量 | 深色值 | 用途 |
|------|--------|------|
| `--color-brand` | `#FF8FB8` | 主品牌色 |
| `--color-pink-soft` | `#FFC1D6` | 柔和粉（标签、指示器） |
| `--color-pink-rose` | `#F29BB7` | 玫瑰粉（渐变、标题） |
| `--color-pink-dusty` | `#D48CA2` | 暗粉（代码属性） |
| `--color-pink-lavender` | `#D5B4FF` | 薰衣草紫（列表标记） |
| `--color-hot` | `#FF5FA2` | 热粉（重要标记） |

### Accent 变体

通过 Style Settings 切换：

- **Classic Pink**（默认）— `#FF8FB8`
- **Vibrant Cyan** — `#00BCD4`
- **Purple** — `#BB86FC`

## 兼容性

- **测试平台**：macOS / Windows / iOS
- **最低版本**：Obsidian v1.0.0
- **推荐插件**：Style Settings、Dataview、Kanban、Calendar

## 贡献

欢迎提交 Issue 和 PR！

## 许可证

MIT License

## 变更日志

### v1.1.0 (2026-05-29)

- 🌸 品牌色从蓝色重构为 Pink Accent System（`#FF8FB8`）
- 🌗 新增完整浅色模式（`.theme-light`）支持
- 💗 新增 6 色粉色变量体系
- 🎨 标题色系从蓝色渐变改为粉紫渐变
- 🖥️ 代码高亮从蓝色系改为粉色系
- 🔗 链接色从蓝色改为粉色（`#FF75AC`）
- 🌑 灰阶从纯灰改为紫灰调（`#6F6870` / `#9B9098`）
- 📄 文件行数从 2290 行增加到 2658 行（+368 行）

### v1.0.3 (2026-05-24)

- 版本号更新

### v1.0.2 (2026-05-24)

- 移除 CSS 中的 `!important`

### v1.0.1 (2026-05-24)

- 移除 manifest.json 中的 screenshot 字段

### v1.0.0 (2026-05-24)

- 初始发布
- Framer 设计系统风格深色主题
- 三种强调色支持
- 17 个可配置功能开关
- Dataview / Kanban / Calendar 插件兼容
- 移动端适配
- 4 个内置 CSS snippets
