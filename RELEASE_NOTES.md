## {{TAG_NAME}}

### 下载

| 平台 | 文件 | 说明 |
|------|------|------|
| Windows x64 | `cursor-i18n-tool-win-x64.exe` | 双击运行即可 |
| macOS Intel | `cursor-i18n-tool-macos-x64` | Intel 芯片 Mac |
| macOS Apple Silicon | `cursor-i18n-tool-macos-arm64` | M1/M2/M3/M4 芯片 Mac |
| Linux x64 | `cursor-i18n-tool-linux-x64` | x86_64 Linux (Ubuntu/Debian 等) |
| Linux ARM64 | `cursor-i18n-tool-linux-arm64` | ARM64 Linux |

### 使用方法

#### Windows
双击 `cursor-i18n-tool-win-x64.exe` 运行，选择「一键汉化」。

#### macOS
```bash
# 赋予执行权限
chmod +x cursor-i18n-tool-macos-arm64

# 运行（首次可能需要右键 → 打开）
./cursor-i18n-tool-macos-arm64
```

> 首次运行如提示「无法验证开发者」，请在系统设置 → 隐私与安全性 → 点击「仍要打开」。
> 汉化工具会自动处理 macOS Gatekeeper 签名问题，无需手动操作。

#### Linux
```bash
# 赋予执行权限
chmod +x cursor-i18n-tool-linux-x64

# 运行
./cursor-i18n-tool-linux-x64
```

### 汉化覆盖范围

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
| **合计** | **1234+** | 持续扩展中 |

### 注意事项

- 每次 Cursor **更新后**需要重新运行汉化
- 部分由服务器动态下发的文案（如模型描述、Cloud Agents 引导）无法翻译
- 建议在汉化前关闭 Cursor 编辑器
