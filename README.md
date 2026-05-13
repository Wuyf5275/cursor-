<div align="center">

# 🀄 Cursor 一键汉化工具

**让你的 Cursor 编辑器说中文 —— 一键翻译，一键还原，零副作用。**

[![Node.js](https://img.shields.io/badge/Node.js-%3E%3D16-green?logo=node.js)](https://nodejs.org)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-blue)](#)
[![License](https://img.shields.io/badge/License-MIT-yellow)](./LICENSE)
[![Release](https://img.shields.io/badge/Release-Latest-orange?logo=github)](https://github.com/huiyi9420/cursor-i18n-tool/releases/latest)

</div>

---

## ✨ 功能亮点

- 🚀 **一键汉化** — 运行即翻译，1200+ 条 UI 文案全覆盖
- ⏪ **一键还原** — 随时恢复英文原版，干净无残留
- 🛡️ **完整性修复** — 自动重算文件校验值，消除「安装已损坏」警告
- 🍎 **macOS 适配** — 自动处理 Gatekeeper 签名（清除属性 → 移除旧签名 → 重签名），免手动 `xattr`
- 🔒 **智能提权** — 权限不足时自动请求管理员权限，无需手动右键
- 💾 **自动备份** — 首次运行自动备份原文件，确保可逆
- 📦 **免安装运行** — 提供独立可执行文件，无需安装 Node.js

## 📸 效果预览

<table>
  <tr>
    <td><img src="./screenshots/preview-general.png" alt="通用设置" width="500"/></td>
    <td><img src="./screenshots/preview-agents.png" alt="智能体设置" width="500"/></td>
  </tr>
  <tr>
    <td align="center"><b>通用设置（General）</b></td>
    <td align="center"><b>智能体设置（Agents）</b></td>
  </tr>
</table>

### 终端运行效果

```
  ┌──────────────────────────────────────┐
  │ ♥ ♠ ♦ ♣ Cursor 一键汉化工具 ♣ ♦ ♠ ♥  │
  │      周四学习钉钉联系我 v1.0.0       │
  │           作者: 不辞水               │
  │     🂡 All in 完美汉化，梭哈！🂡       │
  └──────────────────────────────────────┘

  📂 已定位 Cursor: C:\Users\xxx\AppData\Local\Programs\cursor\resources\app

? 请选择你的策略：
> 🚀  一键汉化 ———— 拿你价值
  ⏪ 恢复英文 ————— 我要验牌
  ──────────────
  ❌ 下周四再见 ———— 小瘪三
```

## 📊 汉化覆盖范围

翻译字典包含 **1234+ 条** 中文翻译，采用四级正则引擎精准匹配：

| 分类 | 条数 | 覆盖内容 |
|------|------|----------|
| 设置页面 - 通用 | ~80 | 语言、自动更新、启动行为等 |
| 设置页面 - 外观/主题 | ~60 | 主题描述、颜色模式、字体设置等 |
| 设置页面 - 智能体 | ~70 | Agent 模式、功能开关、描述文案 |
| 设置页面 - Models | ~40 | API 密钥标签、模型相关设置 |
| 设置页面 - 工作树 | ~30 | 工作树操作、状态提示 |
| 设置页面 - 其他 | ~50 | 通知、菜单栏、快捷键等 |
| 侧边栏/导航标签 | ~20 | Tools & MCPs、Indexing、Docs 等 |
| 聊天/编辑器界面 | ~100 | 输入提示、状态消息、操作确认 |
| 特殊顽固词条 | ~20 | 含模板字符串、转义字符的复杂文案 |
| 其他 UI 文案 | ~700+ | 按钮、提示、对话框、错误信息等 |

> 已验证版本：Cursor **3.3.30** (macOS/Windows)，持续适配新版本。

## 🚀 快速开始

### 方式一：下载可执行文件（推荐，无需安装任何环境）

前往 [Releases 页面](https://github.com/huiyi9420/cursor-i18n-tool/releases/latest) 下载对应平台的可执行文件：

| 平台 | 文件 | 说明 |
|------|------|------|
| Windows x64 | `cursor-i18n-tool-win-x64.exe` | 双击运行即可 |
| macOS Intel | `cursor-i18n-tool-macos-x64` | Intel 芯片 Mac |
| macOS Apple Silicon | `cursor-i18n-tool-macos-arm64` | M1/M2/M3/M4 芯片 Mac |
| Linux x64 | `cursor-i18n-tool-linux-x64` | x86_64 Linux (Ubuntu/Debian 等) |
| Linux ARM64 | `cursor-i18n-tool-linux-arm64` | ARM64 Linux |

<details>
<summary><b>macOS 使用说明</b></summary>

```bash
# 1. 赋予执行权限
chmod +x cursor-i18n-tool-macos-arm64

# 2. 运行
./cursor-i18n-tool-macos-arm64
```

**首次运行提示「无法验证开发者」？**

这是 macOS 安全机制，处理方式任选其一：
- 在终端运行后，前往 **系统设置 → 隐私与安全性 → 点击「仍要打开」**
- 或右键点击文件 → 选择「打开」

> 汉化工具会自动处理 Cursor 应用的 Gatekeeper 签名问题，无需手动执行 `xattr` 或 `codesign`。

</details>

### 方式二：源码运行（适合开发者 / 想要自定义翻译）

**环境要求：**

| 依赖 | 版本 | 说明 |
|------|------|------|
| **Node.js** | ≥ 16（推荐 18+） | [下载地址](https://nodejs.org/zh-cn) |
| **npm** | 随 Node.js 自带 | 用于安装项目依赖 |

> 终端运行 `node -v` 确认已安装 Node.js。

```bash
# 1. 克隆仓库
git clone https://github.com/huiyi9420/cursor-i18n-tool.git
cd cursor-i18n-tool

# 2. 安装依赖
npm install

# 3. 启动（交互式菜单）
node index.js
```

### 命令行静默模式

适合脚本调用或自动化场景：

```bash
# 直接汉化（跳过交互菜单）
node index.js --action=translate

# 恢复英文
node index.js --action=restore
```

## 🏗️ 项目结构

```
cursor-i18n-tool/
├── index.js              # 入口文件：交互菜单 + 提权逻辑
├── src/
│   ├── i18n-core.js      # 核心引擎：正则替换 + Hash 修复 + Gatekeeper
│   ├── dict.js           # 翻译字典：1200+ 条 UI 文案映射
│   └── platform.js       # 平台适配：路径探测 + 权限检测 + 提权
├── .github/workflows/
│   └── release.yml       # CI/CD：自动构建并发布到 GitHub Releases
├── package.json
└── README.md
```

## 🔧 技术原理

### 四级正则匹配引擎

工具采用分层正则策略，精准替换 UI 文案而不破坏代码逻辑：

| 层级 | 策略 | 目标 |
|------|------|------|
| **L1** 顽固词条 | `trickyReplacements` 手工正则 | 含特殊转义、模板字符串 `${}`、内嵌引号的复杂词条 |
| **L2** 安全长句 | `safeMegaRegex` 单次大正则 | 被引号包裹的长句（按长度降序匹配，避免误替换） |
| **L3** 裸文本长句 | `longMegaRegex` 兜底匹配 | ≥20 字符的裸文本（长度保证不与代码变量冲突） |
| **L4** 危险短词 | `riskyRegexes` 上下文感知 | 短词仅在 `children:`、`title:`、`label:` 等 UI 属性中替换 |

### 文件完整性修复

Cursor 启动时会校验核心文件的哈希值，修改后会弹出「安装已损坏」警告。工具会自动：

1. 读取修改后的 `workbench.desktop.main.js`
2. 重新计算哈希值（自动检测 MD5/SHA256/SHA512）
3. 更新 `product.json` 中对应的校验值

### macOS Gatekeeper 处理

在 macOS 上修改 `.app` 包内文件会破坏原始签名，导致 Gatekeeper 阻止启动。工具会自动执行四步修复：

1. **清除扩展属性** — `xattr -cr` 移除隔离标记
2. **移除旧签名** — `codesign --remove-signature` 清除残留的公证票据
3. **重新签名** — `codesign --force --deep --sign -` 使用 ad-hoc 签名
4. **再次清除** — `xattr -cr` 清除签名过程可能引入的新属性

## 📦 自动构建发布

本项目使用 GitHub Actions 自动构建，打 tag 即触发发布：

```bash
# 发布新版本
git tag v1.1.0
git push origin v1.1.0
```

工作流会自动：
1. 在 Windows/macOS/Linux 上构建五个平台的可执行文件
2. 创建 GitHub Release
3. 上传构建产物作为 Release 资产

> 手动触发也可在仓库 Actions 页面点击「Run workflow」。

## 🤝 贡献指南

### 添加新的翻译词条

编辑 `src/dict.js`，在对应字典中添加条目：

```javascript
// 安全长句（≥3 个单词或含特殊字符的句子）→ safeGlobalDict
"Your english text here": "你的中文翻译",

// 危险短词（1-2 个单词，可能与代码变量冲突）→ riskyShortWords
"Settings": "设置",
```

**选择字典的原则：**

| 条件 | 字典 | 原因 |
|------|------|------|
| ≥3 个单词 / 含特殊字符 | `safeGlobalDict` | 足够独特，全局替换不会误伤代码 |
| 1-2 个单词 | `riskyShortWords` | 仅在 UI 属性上下文中替换，避免破坏代码变量 |
| 含模板字符串 / 转义字符 | `trickyReplacements` | 需要手工编写正则处理 |

### 处理特殊格式的词条

如果词条包含模板字符串（如 `${variable}`）、转义字符、Unicode 转义（如 `\u2019`）或其他需要特殊处理的格式，请添加到 `i18n-core.js` 的 `trickyReplacements` 数组中，编写专属正则。

## ⚠️ 注意事项

- 每次 Cursor **更新后**需要重新运行汉化（更新会覆盖修改过的文件）
- 工具会自动备份原文件（`.backup` 后缀），可随时还原
- **部分文案无法翻译**：由服务器动态下发的文案（如模型描述、Cloud Agents 引导任务）不在本地文件中
- 建议在汉化前**关闭 Cursor 编辑器**
- ⚠️ **请勿向 `riskyShortWords` 添加通用单词**（如 Error、File、View 等），会导致 Cursor 白屏崩溃

## 📄 开源许可

[MIT License](./LICENSE) — 随便用，开心就好。

## 🙏 致谢

- 感谢所有为翻译词条做出贡献的小伙伴 —— 海洋饼干、诺导、发发、苗苗、蓉蓉、木木文、蜗牛、杨书记
- 基于 [不辞水](https://github.com/Wuyf5275/cursor-i18n-tool) 的原始项目扩展，感谢原作者

---

<div align="center">

**如果这个工具帮到了你，请给个 ⭐ Star 支持一下！**

*Fork of [Wuyf5275/cursor-i18n-tool](https://github.com/Wuyf5275/cursor-i18n-tool) with expanded translations*

</div>
