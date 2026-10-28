# A second editor

Status: not installed and not tested. The steps are generic on purpose. They do not assume a particular product beyond “this editor can be given a standing instruction, or the person can paste one.”

## Standing instruction

If the editor reads a project file such as `AGENTS.md` or a rules directory, append `setup/AGENTS.fragment.md` there. Set the folder path. Start a new session and check that the agent names the files it opened.

If you cannot tell whether the editor loaded the file, it did not. Use the paste block.

## Paste block

`setup/session-start.txt` is the path that does not depend on the editor. Paste it at the start of the chat and fill in the folder path. This is the setup to use until a standing instruction has been shown to load.

## What was not tested

- No second editor was opened.
- No rule screen was clicked.
- No check was run on Windows, Linux, or macOS editor settings.

Cursor’s own snippet is in `setup/cursor.md`. It is also untested in a live chat.
