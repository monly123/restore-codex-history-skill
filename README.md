# Restore Codex History Skill

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
