# Ledger

Append only. Rules: `../../PROTOCOL.md` section 9.

An open claim is a `start` whose id has no later `done`, `conflict`, or `released`.

| id | at | agent | files | saw_revision | status | note |
|---|---|---|---|---|---|---|
| N-1 | 2026-03-03T09:00:00Z | North | INDEX.md, NOW.md, LEDGER.md, RECORD.md | none yet | start | Open the March issue. |
| N-1 | 2026-03-03T09:20:00Z | North | INDEX.md, NOW.md, LEDGER.md, RECORD.md | NOW 1, RECORD 1 | done | D-001 and A-001 written. Next owner is South. |
| S-1 | 2026-03-03T11:00:00Z | South | NOW.md, sessions/2026-03-03-south.md | NOW 1 | start | Masthead. |
| N-2 | 2026-03-03T16:00:00Z | North | RECORD.md | RECORD 1 | start | Page-size correction. NOW.md left alone because S-1 is open on it. |
| N-2 | 2026-03-03T16:20:00Z | North | RECORD.md | RECORD 2 | done | F-001, C-001, D-002. A-001 superseded. |
| N-3 | 2026-03-03T16:25:00Z | North | NOW.md | NOW 1 | start | Tried to cite D-002 from NOW.md. |
| N-3 | 2026-03-03T16:26:00Z | North | NOW.md | NOW 1 | conflict | S-1 already reserved NOW.md. No write. Text parked in drafts/N-3.md. |
| S-1 | 2026-03-04T09:10:00Z | South | NOW.md, sessions/2026-03-03-south.md | NOW 1, wrote NOW 2 | done | Resumed. The 11:20 checkpoint had landed; the ledger close had not. Re-read RECORD.md. NOW.md revision 2 cites D-002. Partial: masthead still unwritten. |
