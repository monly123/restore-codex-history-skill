# Restore Codex History Skill

用于诊断和修复 Codex Desktop 或 Codex CLI 聊天记录丢失问题的 Codex skill。

它可以帮助处理：

- Codex Desktop 侧边栏聊天记录不显示
- 从原始 JSONL 会话重建 `session_index.jsonl`
- 检查 `state_*.sqlite` 线程元数据
- 修复 `model_provider`、归档状态、来源和 `cwd` 项目分组问题

## 安装

从最新 GitHub Release 下载 `restore-codex-history-skill.tar.gz`，然后运行：

```bash
mkdir -p ~/.codex/skills
tar -xzf restore-codex-history-skill.tar.gz -C ~/.codex/skills
```

## 使用

先从 dry-run 诊断开始：

```bash
python3 ~/.codex/skills/restore-codex-history/scripts/restore_codex_history.py diagnose
```

会修改数据的修复命令都需要显式加上 `--apply`，并会在 `~/.codex/manual_restore_backup_*` 下创建带时间戳的备份。

## 安全说明

这个 skill 默认采用保守策略。先检查，再备份，只有在确认对话确实属于某个项目时，才重新分配项目路径。

## Release 附件

`restore-codex-history-skill.tar.gz` 的 SHA-256：

```text
62a02e52a482c20c9a16faba44386cc583b2ea5e47f9d6ac997d359f3ee904b5
```

## English

Codex skill for diagnosing and repairing missing Codex Desktop or Codex CLI chat history.

It can help with:

- Missing conversations in the Codex Desktop sidebar
- `session_index.jsonl` rebuilds from raw JSONL sessions
- `state_*.sqlite` thread metadata checks
- `model_provider`, archive, source, and `cwd` project grouping issues

## Install

Download `restore-codex-history-skill.tar.gz` from the latest GitHub Release, then run:

```bash
mkdir -p ~/.codex/skills
tar -xzf restore-codex-history-skill.tar.gz -C ~/.codex/skills
```

## Use

Start with a dry-run diagnosis:

```bash
python3 ~/.codex/skills/restore-codex-history/scripts/restore_codex_history.py diagnose
```

Mutating repair commands require `--apply` and create timestamped backups under `~/.codex/manual_restore_backup_*`.

## Safety

This skill is intentionally conservative. Inspect first, back up before writing, and only reassign project paths when the conversation clearly belongs to that project.

## Release Asset

SHA-256 for `restore-codex-history-skill.tar.gz`:

```text
62a02e52a482c20c9a16faba44386cc583b2ea5e47f9d6ac997d359f3ee904b5
```
