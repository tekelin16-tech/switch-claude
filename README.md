# switch-claude

一個互動式 Bash 腳本，用於在不同 AI 後端之間快速切換，並透過 tmux 管理 Claude Code sessions。

## 功能

- 🔄 快速切換 Claude Code 的 AI 後端（官方版 / DeepSeek）
- 📋 列出並 attach 到現有的 tmux sessions
- 🗑️ 管理（清除）執行中的 sessions
- 📝 自動記錄 session 啟動與結束日誌
- ✨ 支援 Claude Code Workflows（`CLAUDE_CODE_WORKFLOWS=1`）

## 環境需求

- tmux
- [Claude Code](https://claude.ai/code)
- Bash

## 安裝

```bash
cp switch-claude ~/.local/bin/switch-claude
chmod +x ~/.local/bin/switch-claude
```

## 設定

```bash
mkdir -p ~/.claude/configs
```

**~/.claude/configs/official.json**
```json
{ "model": "claude-sonnet-4-5" }
```

**~/.claude/configs/deepseek.json**
```json
{ "apiBaseUrl": "https://api.deepseek.com", "model": "deepseek-chat" }
```

## 使用方式

```bash
switch-claude
```

| 選項 | 說明 |
|------|------|
| 官方訂閱版 (Official) | 使用 Anthropic 官方 Claude |
| DeepSeek 版 (v4) | 使用 DeepSeek API |
| 🗑️ 管理 Session | 查看 / 關閉現有 sessions |
| 取消退出 | 離開腳本 |

## tmux 操作

| 按鍵 | 功能 |
|------|------|
| `Ctrl+B` 再按 `D` | 離開（Claude 繼續在背景執行） |
| `switch-claude` 再選同版本 | Attach 回現有 session |

## 日誌

```
~/Desktop/openclaw-logs/session.log
```

## 授權

MIT
