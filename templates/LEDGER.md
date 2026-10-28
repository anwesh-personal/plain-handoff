# Ledger

Append only. Do not edit or delete a row. Rules: `PROTOCOL.md` section 9.

Statuses: `start` | `done` | `conflict` | `released`

An open claim is a `start` whose id has no later `done`, `conflict`, or `released`.

| id | at | agent | files | saw_revision | status | note |
|---|---|---|---|---|---|---|
