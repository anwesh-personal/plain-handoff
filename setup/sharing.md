# Sharing the folder

Default: one ordinary folder. Each editor gets its own short instruction that names that folder. See `cursor.md` and `other-editor.md`.

## Why a copy can drift

The instruction file and the handoff folder are separate. If you edit `PROTOCOL.md` and forget the instruction, an editor may follow an old revision. Both files carry `protocol_revision`. Session start should say the number it read.

## Symlinks

A symlink is a path that points at another path. It is optional. Plain Handoff 0.1 does not create one, and none was tested here.

Use a symlink only when you already know the editor will follow it, and only from the editor’s instruction location to the handoff folder. Keep the handoff folder itself free of links.

Risks:

- A broken link looks like a missing file. The agent may skip the protocol and say nothing useful. If `INDEX.md` does not open, stop and say the link is broken.
- macOS and Linux create a symlink with `ln -s`. The link stores the target path. Moving the folder breaks it.
- Windows often refuses symlink creation unless the account is allowed to create them. A normal copy is the reliable option there. A copy does not update itself.
- Git stores a symlink as the target path. If you commit a link whose target is a private directory, you publish that path. If a tool copies through the link, you can publish the private files. Do not link a home directory, a credentials store, a private repository, or a personal memory folder into a folder you might share.
- Do not put the handoff folder inside a repository you do not intend to publish, and then link that folder out to a public one.

The plain-folder alternative is the copy in the root `README.md`. Two copies are safe when you compare revisions before writing, and unsafe when you forget to.
