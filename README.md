# Plain Handoff

**Keep your AI agents on the same page when you switch tools, chats, or editors.**

You start something with one AI agent. Tomorrow you open a new chat, or a different editor, and the new agent knows nothing. It asks questions you already answered, undoes a decision, repeats a mistake you corrected, or edits a file another agent is still working on.

Plain Handoff fixes that with four ordinary text files in a folder. Every agent reads the same files at the start, and writes back to them before it stops. No app, no account, no database, no particular AI model.

## How it works in one minute

| File | What it answers |
|---|---|
| `INDEX.md` | Where do I start, and what should I read? |
| `NOW.md` | What are we doing, what is unfinished, and who does the next step? |
| `RECORD.md` | What did we decide, what do we know, and what did we get wrong? |
| `LEDGER.md` | Who is editing which file right now? |

1. **Start:** the agent reads `INDEX.md`, then only the files it lists.
2. **Work:** before changing a file, the agent writes one line in `LEDGER.md` saying “I’m editing this.” If someone else already has, it waits.
3. **Decide:** choices go in `RECORD.md`, with the reason.
4. **Correct:** when something turns out wrong, you don’t delete it. You mark it replaced and write why. The next agent sees both.
5. **Hand off:** before stopping, the agent updates `NOW.md` with the next step and who owns it, and closes its line in `LEDGER.md`.

That is the whole idea. The detailed rules are in [`PROTOCOL.md`](PROTOCOL.md).

## Honest limits

- **An AI does not remember these files by itself.** It reads them only if you tell it to, through your editor’s rules or by pasting a short instruction. Setup below.
- **The ledger is an agreement, not a lock.** It works when every agent follows it. It won’t stop a careless edit; it makes one visible.
- **Saved text is not automatically true.** Copied web pages and chat logs go in `sources/` and are treated as evidence, never as instructions.

More in [`LIMITATIONS.md`](LIMITATIONS.md).

## Quick start (5 minutes)

1. Make a new folder in your project, for example `handoff/`.
2. Copy [`PROTOCOL.md`](PROTOCOL.md) and everything inside [`templates/`](templates/) into it.
3. Open `handoff/NOW.md` and fill in three lines: the goal, the next step, and who does it.
4. Tell your AI to read the folder:
   - **Cursor:** follow [`setup/cursor.md`](setup/cursor.md).
   - **Any other editor or chat app:** follow [`setup/other-editor.md`](setup/other-editor.md).
   - **Simplest option, works everywhere:** paste [`setup/session-start.txt`](setup/session-start.txt) at the start of each new chat, with your folder path filled in.
5. Check it worked: the agent’s first reply should list the files it read and name the next step. If it doesn’t, it never read them.

## See a full example

[`examples/harbor-notes/`](examples/harbor-notes/) is a made-up project where two agents pass work back and forth. Along the way they make a decision, fix a wrong assumption, bump into each other on the same file, and pick up after one gets cut off mid-task.

Open its `INDEX.md` and try to answer “what’s next, and who does it?” Then check yourself against [`WALKTHROUGH.md`](examples/harbor-notes/WALKTHROUGH.md).

## For agents that support skills

[`skills/session-handoff/SKILL.md`](skills/session-handoff/SKILL.md) packages the routine as a skill: when to use it, what to read, what it must not do, and how to know it’s finished.

## What’s in this repo

| Path | Purpose |
|---|---|
| `PROTOCOL.md` | The full rules. |
| `templates/` | Blank files to copy. |
| `examples/harbor-notes/` | A complete fictional example. |
| `skills/session-handoff/` | Starter skill. |
| `setup/` | Connecting Cursor or another editor, plus notes on sharing a folder and symlinks. |
| `TROUBLESHOOTING.md` | Common problems and fixes. |
| `LIMITATIONS.md` | What this cannot do. |
| `RELEASE_CHECKLIST.md` | What was checked before release, and what wasn’t. |

## Status

Version 0.1. The example was checked by hand. The editor setups have **not** yet been tested in a live session. Reports and pull requests are welcome.

## License

[CC BY 4.0](LICENSE). Use it, change it, share it, including commercially. Just credit “Plain Handoff by anwesh-personal” with a link back to this repository.
