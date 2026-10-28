# Limitations

- An agent uses the folder only in a conversation whose instructions told it to read `INDEX.md`. A later chat, a different editor, or a model with no instruction file will not pick the folder up by itself.
- Claims coordinate writers who follow them. They do not stop another program from editing the same file.
- The revision number catches a stale write only when both sides update it and check it.
- There is no access control, encryption, or audit beyond the text you write.
- Superseded notes stay until a person archives or leaves them. The protocol does not delete them for you.
- `review_after` does nothing unless a session actually performs the review.
- Copied editor instructions go stale when `protocol_revision` changes and the copy is not updated.
- A credential you type into `NOW.md` is now in that file. The protocol cannot take it back out of a copy you already shared.
- Plain Handoff 0.1 was not installed in Cursor and was not run in a second editor. The Harbor Notes files were checked by reading them. That is not a test of an editor’s rule loader.
- Symlinks were not created and were not tested.
