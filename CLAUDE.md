# CLAUDE.md — Project Context

This repo also doubles as a persistent home for Sohil's KDP (Kindle Direct Publishing — coloring books) business automation context, so that behavior set up for him carries over into future Claude Code sessions in this repo.

## Standing behavior: Task → Feature Playbook

Sohil runs a KDP coloring-book business. He has asked that **whenever he describes any task** (Amazon keyword research, cover design, listing writing, ads optimization, weekly review, pre-publish checks, account-safety, or anything else), Claude should:

1. Read `kdp-task-feature-playbook.md` in this repo root first.
2. If the task already has an entry, answer directly: "ye kaam [feature A] + [feature B] se hoga" — with brief reasoning, no need to re-derive from scratch.
3. If the task has no entry yet, reason it out (which Claude Code / Claude app feature(s) or installed skill(s) solve it), answer Sohil, **and append a new entry** to `kdp-task-feature-playbook.md` in the same format, so the playbook keeps growing.

Do this automatically — Sohil should never have to ask "check the playbook" or re-explain this instruction; it applies by default in every session that loads this file.

## Standing behavior: New-feature watch

An hourly Routine (see Routines list) fetches Claude's official release-notes pages, diffs them against `.claude/release-notes-snapshot.json`, and when something new appears:
- Summarizes the new feature/change
- Appends a relevant entry (or updates an existing one) in `kdp-task-feature-playbook.md` if it's relevant to a KDP workflow
- Updates the snapshot file
- Commits the changes
- Notifies Sohil with a one-line summary

This is a **best-effort hourly check**, not instant/real-time — there is no push notification from Anthropic when a feature ships; this is the closest practical mechanism (minimum Routine interval is ~1 hour).

Official sources being watched:
- Claude Code changelog: https://code.claude.com/docs/en/changelog
- Claude Apps release notes: https://docs.claude.com/en/release-notes/claude-apps
- Claude Platform release notes: https://docs.claude.com/en/release-notes/overview

## Files in this repo relevant to this context
- `kdp-task-feature-playbook.md` — the living task→feature reference
- `.claude/release-notes-snapshot.json` — last-seen snapshot of the three release-notes pages, used to detect what's new
