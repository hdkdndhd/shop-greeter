# CLAUDE.md — Project Context

This repo is a persistent home for a standing behavior, so it carries over into every future Claude Code session here.

## Standing behavior: Task → Feature Playbook

Whenever a task is described — any task, any domain — delegate to the **`task-feature-router`** subagent (defined in `.claude/agents/task-feature-router.md`). It owns `task-feature-playbook.md`: it looks up or creates the entry and reports back which feature(s) solve the task. Relay its answer to the user directly, and if it added a new playbook entry, commit the change.

Do this automatically — never wait to be asked "check the playbook" or "use the router agent"; it applies by default in every session that loads this file.

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
