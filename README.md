# Framer Theme

> 一款受 Framer 设计系统启发的 Obsidian 深色主题，黑白配色 + 鲜明蓝色强调色。

![screenshot](https://raw.githubusercontent.com/TheViviana/Obsidian-Theme-Framer/main/screenshot.png)

## 特性

- 🎨 **三种强调色** — 经典蓝 / 活力青 / 紫色，一键切换
- 🖼️ **Framer 设计语言** — 极简黑白底色，280px 属性面板，紧凑 UI
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
2. Accent Style → 选择 Classic Blue / Vibrant Cyan / Purple

### 内置功能开关

| 功能 | 默认 | 说明 |
|------|------|------|
| Framed Tab Headers | 开启 | 标签页边框样式 |
| Section Highlights | 开启 | 设置侧栏高亮 |
| Quick Actions Style | 开启 | 命令面板 Framer 风格 |
| Reading Mode Prose | 开启 | 阅读模式优化 |
| Canvas Grid | 开启 | 编辑器网格背景 |
| 280px Property Panel | 开启 | 右侧面板固定宽度 |
| Compact 4px Spacing | 关闭 | 更紧凑的间距 |

### 内置 CSS Snippets

以下样式默认启用，无需额外安装：

- **Bold Pink** — 加粗文字显示为粉色 `#FF69B4`
- **Immersive Translate Red** — 翻译结果显示红色渐变
- **Minimal Tables** — 表格自动撑满、简洁边框
- **Floating Status Bar** — 状态栏悬停滑入

如需关闭，需删除 `theme.css` 末尾对应的 CSS 块。

## 截图

<!-- 建议提供以下截图 -->
1. **编辑器** — 展示代码、表格、标签页、文件侧栏
2. **阅读模式** — 展示排版效果
3. **设置面板** — 展示 Style Settings 选项

## 兼容性

- **测试平台**：macOS / Windows / iOS
- **最低版本**：Obsidian v1.0.0
- **推荐插件**：Style Settings、Dataview、Kanban、Calendar

## 贡献

欢迎提交 Issue 和 PR！

## 许可证

MIT License

## 变更日志

### v1.0.0 (2026-05-24)

- 初始发布
- Framer 设计系统风格深色主题
- 三种强调色支持
- 17 个可配置功能开关
- Dataview / Kanban / Calendar 插件兼容
- 移动端适配
- 4 个内置 CSS snippets
