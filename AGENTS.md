# AGENTS.md — ff14-keybound-brawler

工作区长期约定见 `..\AGENTS.md`，其中第 3 节「FF14 游戏内数据读取约定」对本项目强制生效。

需要读取游戏内真实数据（聊天文本、addon 名、副本/区域名、界面开关时序、角色/职业状态等）时：

- 先读 AgentLogBridge 导出目录（默认 `%APPDATA%\XIVLauncherCN\pluginConfigs\AgentLogBridge\export\`）。
- 用 `..\dalamud-agent-bridge\tools\ff14log.py`，顺序：`dir` → `status` → `tail -n 20` → `summary --hours 3` → `search 关键词`。
- 不要把记忆里的 addon 名 / 聊天文本当真；日志里没有就直说，并给出替代（让用户看 `/albridge` 窗口或提供截图）。
- 导出目录只读。需要多采集字段时走 `..\dalamud-agent-bridge\` 项目，不要在本项目里另写读日志逻辑。
