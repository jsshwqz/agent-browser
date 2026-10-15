# agent-browser — AionUi Skill Wrapper

基于 [agent-browser](https://github.com/vercel-labs/agent-browser) 的 AionUi 技能封装，为 AI Agent 提供浏览器自动化能力。

> ⚠️ **重要**：本仓库仅分发 skill 封装文档，**不重分发 agent-browser 二进制**。
> agent-browser 本体请从 npm 官方源安装。

---

## 原始项目致谢

本项目是对以下开源项目的使用封装与文档适配：

- **项目**: [agent-browser](https://github.com/vercel-labs/agent-browser)
- **作者**: Vercel Labs
- **授权**: Apache License 2.0
- **版权**: © 2026 Vercel Labs
- **Stars**: 44,000+

agent-browser 是一款 Rust 原生的浏览器自动化 CLI，提供 100+ 命令，专为 AI Agent 设计（无障碍树 + ref 工作流）。

## 本封装包含什么

```
├── LICENSE              # Apache-2.0 全文
├── NOTICE               # 上游版权 + 变更声明
├── README.md            # 本文件
├── .gitignore
├── SKILL.md             # AionUi skill 入口
├── references/          # 深度参考文档
│   ├── advanced.md      # 高级工作流
│   ├── actions.md       # 命令速查
│   ├── authentication.md# 认证处理
│   ├── forms.md         # 表单填写
│   ├── recording-screens.md # 录制与截图
│   └── skills.md        # 工作流示例
└── templates/           # 可复用模板
    ├── auth-form-test.md
    ├── element-discovery.md
    └── test-automation.md
```

## 安装

### 1. 安装 agent-browser（本体，必需）

```bash
# Windows
npm install -g agent-browser

# macOS
brew install agent-browser

# Linux
npm install -g agent-browser
agent-browser install --with-deps
```

### 2. 安装本 Skill 封装

将本仓库克隆到 AionUi 的 skills 目录：

```bash
git clone <your-repo-url> ~/.config/aionui/skills/agent-browser
# 或 macOS
git clone <your-repo-url> ~/Library/Application\ Support/aionui/skills/agent-browser
```

## 快速开始

```bash
# 打开网页并截图
agent-browser open https://example.com
agent-browser screenshot page.png
agent-browser close
```

### Windows 用户

系统 Chrome 路径通常为 `C:\Program Files\Google\Chrome\Application\chrome.exe`，建议指定：

```bash
agent-browser --executable-path "C:\Program Files\Google\Chrome\Application\chrome.exe" open https://example.com
```

## 常用命令

| 操作 | 命令 |
|------|------|
| 打开页面 | `agent-browser open <url>` |
| 截图 | `agent-browser screenshot [path]` |
| 无障碍树 | `agent-browser snapshot -i` |
| 点击元素 | `agent-browser click @e1` |
| 填充输入 | `agent-browser fill @e1 "text"` |
| 执行 JS | `agent-browser eval "document.title"` |
| 语义定位 | `agent-browser find role button click --name "Submit"` |
| 等待元素 | `agent-browser wait "#selector"` |
| 批量执行 | `agent-browser batch "open https://..." "click @e1"` |
| 获取文本 | `agent-browser get text @e1` |
| 关闭浏览器 | `agent-browser close` |

完整命令参考：`agent-browser --help` 或查看 `references/advanced.md`

## 许可

- 本 Skill 封装文档：Apache-2.0（见 LICENSE）
- agent-browser 本体：Apache-2.0（© Vercel Labs）

详见 [NOTICE](NOTICE) 文件获取完整归属信息。

## 参与贡献

欢迎提交 Issue 和 Pull Request。提交前请确认：

1. 保留 LICENSE 和 NOTICE 文件完整性
2. 不要删除或修改上游版权声明
3. 修改代码时标注变更说明

## 许可证

```
Copyright 2026 jsshwqz
Licensed under Apache License, Version 2.0
```
