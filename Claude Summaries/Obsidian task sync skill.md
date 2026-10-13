---
type: claude-summary
session_id: local_b721b780-2a4d-4d1c-98f4-56378529c45e
session_title: Obsidian task sync skill
last_synced: 2026-10-12
status: active
tags: [claude-summary, claude-skill, obsidian, automation]
---

# Obsidian TODO Sync skill

## Context
Built a Claude skill, `obsidian-todo-sync`, with skill-creator. It gathers unchecked checkboxes from across the Obsidian vault into one master to-do list and moves completed items to a closed list. It was then added to the existing **Morning brief** scheduled task.

## Artifacts
- **Skill:** `obsidian-todo-sync` (installed). It runs a bundled script, `scripts/todo_sync.py`.
  - Preview, no changes: `--vault <path> --vault-name notes`
  - Write changes: add `--apply`
  - Other options: `--todo <path>` (default `TODO.md`), `--date M/D/YYYY`
- **Vault:** `/Users/kcyr/notes/notes`. This is a git repo, so `git diff` shows and can revert every change.
- **Master list:** `TODO.md` at the vault root, with `### Open Items` and `### Closed Items` headings.
- **Scheduled task:** "Morning brief", weekdays at 8:10 AM. Updated to run the sync first.

## How the skill works
1. **Closes finished items.** Checked `- [x]` lines under Open Items move unchanged to the bottom of Closed Items.
2. **Gathers open items.** Every `- [ ]` in other notes is added to Open Items in this format: `- [ ] <text> - [<Note>](obsidian://open?vault=notes&file=<encoded path>) - M/D/YYYY`.
3. **Updates the source note.** `- [ ]` becomes `- ` in the source note, keeping its indentation.

It skips `TODO.md`, `Screenshots/`, `.obsidian/`, `.git/`, `.trash/`, and notes whose names start with `Morning Brief`. It ignores checkboxes in code blocks and alternate states like `[-]` and `[/]`. Duplicate items aren't added twice, and running it again changes nothing. If either heading is missing, it stops with an error.

## Decisions
- When you run it yourself, it shows a preview and asks before writing. In the scheduled run it writes automatically, because no one is there to approve.
- It's a safety stop: if an item looks like it contains card, account or customer data, the sync is skipped and the brief shows a warning.
- **Morning brief order:**
  1. Save the list of yesterday's notes first, because the sync changes file modified dates.
  2. Run the sync.
  3. Show the full Open Items list from `TODO.md`, plus a one-line summary of what the sync changed.
- The brief's old step that scanned every note for checkboxes was removed.

## Results to date
- First live run: 10 items added (Q2: 1, Taylor: 7, PSE Opportunity Manager: 2). Nothing closed, because the placeholder Toast item wasn't checked.
- Alacriti, Bakkt, Meijer and REAL showed as changed in git from edits made before the session. The skill didn't change them.

## Open items / next steps
- Check off an Open Item (e.g., the Toast placeholder) and run again to confirm items move to Closed Items.
- Click **Run now** on the Morning brief task once to approve file access, so scheduled runs don't stop to ask.
- Delete the stray `obsidian-todo-sync-review.html` from the vault root (Claude couldn't delete it).
- Optional: tune the skill description so it triggers more reliably.

## Resume prompt
> I'm continuing work on my `obsidian-todo-sync` skill. It gathers `- [ ]` checkboxes from my vault (`/Users/kcyr/notes/notes`) into the Open Items list in `TODO.md`, moves checked items to Closed Items, and turns source checkboxes into plain bullets, using `scripts/todo_sync.py` (`--apply` writes changes). It runs first in my weekday 8:10 AM "Morning brief" scheduled task, which then shows the Open Items list. Please help me with: [next task].
