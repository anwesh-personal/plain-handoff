# Cursor

Status: the snippet below is written for Cursor’s project-rule format. It was not installed in a Cursor project, and no Cursor session was run to see whether it loads.

## Plain folder

1. Create the handoff folder as in the root `README.md`.
2. Copy `setup/plain-handoff.mdc` into that project’s `.cursor/rules/` directory.
3. Edit the one path in the snippet so it points at the handoff folder.
4. Start a new chat. The first reply should name the files it opened. If it does not, the rule is not in effect for that chat. Paste `setup/session-start.txt` instead.

Do not point the path at a private project, a home directory, or a store of credentials. Do not add this rule inside someone else’s repository unless they asked you to.

A rule file in a project is a second copy of the instruction. When you change `PROTOCOL.md`, compare `protocol_revision` with the number in the rule. Update the rule if the revision changed.

## Symlink

Optional. Not used by this release. Read `setup/sharing.md` before you create one. The plain copy above is the setup this folder documents.
