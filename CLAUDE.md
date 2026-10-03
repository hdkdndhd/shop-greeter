# CLAUDE.md — Project Context

This repo doubles as a persistent home for a standing behavior Sohil has asked for, so it carries over into every future Claude Code session in this repo — not scoped to KDP or any one domain.

## Standing behavior: Task → Feature Playbook (ANY task, not KDP-specific)

Sohil has asked that **whenever he describes any task — any domain, KDP or not** — Claude should:

1. Read `task-feature-playbook.md` in this repo root first.
2. If the task already has an entry, answer directly: "ye kaam [feature A] + [feature B] se hoga" — with brief reasoning, no need to re-derive from scratch.
3. If the task has no entry yet, reason it out (which Claude Code / Claude app feature(s), built-in tool(s), connector(s), or installed skill(s) solve it), answer Sohil, **and append a new entry** to `task-feature-playbook.md` in the same format, so the playbook keeps growing — regardless of whether the task is KDP-related, coding, writing, research, anything.

Do this automatically — Sohil should never have to ask "check the playbook" or re-explain this instruction; it applies by default in every session that loads this file. **This is general-purpose — do not filter or restrict entries to KDP topics.**

## Standing behavior: New-feature watch

An hourly Routine (see Routines list) fetches Claude's official release-notes pages, diffs them against `.claude/release-notes-snapshot.json`, and when something new appears:
- Summarizes the new feature/change
- Adds/updates an entry in `task-feature-playbook.md` for whatever task(s) that new feature would help with — **any domain, not filtered to KDP**
- Updates the snapshot file
- Commits the changes
- Notifies Sohil with a one-line summary (only when something genuinely new was found, to avoid noisy hourly pings)

This is a **best-effort hourly check**, not instant/real-time — there is no push notification from Anthropic when a feature ships; this is the closest practical mechanism (minimum Routine interval is ~1 hour).

Official sources being watched:
- Claude Code changelog: https://code.claude.com/docs/en/changelog
- Claude Apps release notes: https://support.claude.com/en/articles/12138966-release-notes
- Claude Platform release notes: https://platform.claude.com/docs/en/release-notes/overview

## Files in this repo relevant to this context
- `task-feature-playbook.md` — the living task→feature reference (general-purpose, any domain)
- `.claude/release-notes-snapshot.json` — last-seen snapshot of the three release-notes pages, used to detect what's new
