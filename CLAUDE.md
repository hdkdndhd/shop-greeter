# CLAUDE.md — Project Context

This repo is a persistent home for a standing behavior, so it carries over into every future Claude Code session here.

## Standing behavior: Task → Feature Playbook

Whenever a task is described — any task, any domain — Claude should:

1. Read `task-feature-playbook.md` in this repo root first.
2. If the task already has an entry, answer directly: "ye kaam [feature A] + [feature B] se hoga" — with brief reasoning, no need to re-derive from scratch.
3. If the task has no entry yet, reason it out (which Claude Code / Claude app feature(s), built-in tool(s), connector(s), or installed skill(s) solve it), answer directly, **and append a new entry** to `task-feature-playbook.md` in the same format, so the playbook keeps growing.

Do this automatically — never wait to be asked "check the playbook"; it applies by default in every session that loads this file.

## Standing behavior: New-feature watch

An hourly Routine fetches Claude's official release-notes pages, diffs them against `.claude/release-notes-snapshot.json`, and when something new appears:
- Summarizes the new feature/change
- Adds/updates an entry in `task-feature-playbook.md` for whatever task(s) that new feature would help with
- Updates the snapshot file
- Commits the changes
- Sends a short one-line notification (only when something genuinely new was found, to avoid noisy hourly pings)

This is a **best-effort hourly check**, not instant/real-time — there is no push notification from Anthropic when a feature ships; this is the closest practical mechanism (minimum Routine interval is ~1 hour).

Official sources being watched:
- Claude Code changelog: https://code.claude.com/docs/en/changelog
- Claude Apps release notes: https://support.claude.com/en/articles/12138966-release-notes
- Claude Platform release notes: https://platform.claude.com/docs/en/release-notes/overview

## Files in this repo relevant to this context
- `task-feature-playbook.md` — the living task→feature reference
- `.claude/release-notes-snapshot.json` — last-seen snapshot of the three release-notes pages, used to detect what's new
