---
name: statement-ingest
description: Ingest account statements (PDF/CSV/image) into the user's
  private cartridge — fetch or receive files, handle password-protected
  PDFs, extract balances and transactions, and update snapshot.md with
  evidence-grade numbers. Use whenever the user provides statements or
  asks to refresh their snapshot from documents.
---

# Statement Ingest

Turn raw account statements into an updated `cartridges/private/snapshot.md`.
Statements are evidence; they override the user's estimates (see
`onboarding/level-1-build.md` — evidence beats estimates, always).

## 1. Acquire

- Ask the user to provide statements: file upload, a local path, or — if
  you have tools (Drive/email MCP) — offer to fetch them yourself.
- **Freshness:** running month or the month before is ideal. Hard cap: 3
  months. Refuse older files; if freshest evidence is 2–3 months old, use
  it but set `as_of` to the statement cut date, not today.
- Store every file in `cartridges/private/statements/YYYY-MM/<institution>.pdf`
  (YYYY-MM = statement cut month, not download date). **Never store
  statements anywhere else in the repo.** Verify protection:
  `git check-ignore cartridges/private/statements/YYYY-MM/<file>`.

## 2. Decrypt (password-protected PDFs)

Some banks password-protect statements (e.g., in Mexico: Stori does;
BBVA, Banamex, AMEX, Mercado Pago typically don't).

- Detect: `qpdf --is-encrypted file.pdf` (exit 0 = encrypted), or the
  read simply fails.
- Ask the user for the password. **Never write the password to any file,
  log, or commit message. Do not echo it back.**
- Decrypt to a sibling copy:
  `qpdf --decrypt --password='<PWD>' stori.pdf stori-decrypted.pdf`
- If `qpdf` is missing: `brew install qpdf` (macOS) / `pacman -S qpdf` or
  `apt install qpdf` (Linux). Fallback tool: `pikepdf` (Python).
- Optional, for recurring use: suggest the user store statement passwords
  in a password manager; with 1Password CLI they can supply it as
  `qpdf --decrypt --password="$(op read 'op://vault/item/password')" ...`
  so the password never touches the chat or shell history in plaintext.

## 3. Extract

From each statement, pull what the snapshot schema needs
(`cartridges/SPEC.md`):

- Closing balance per account (and cut date)
- For credit/loan statements: balance, annual rate (CAT/APR as stated),
  minimum payment, payment due date
- Income deposits (payroll pattern) — distinguish gross vs. what lands
- Transactions for the discretionary breakdown: groceries, restaurants/
  delivery, transport, subscriptions, and itemize "misc"
- Flag business-vs-personal charges and equity-building payments
  (mortgage/preventa) per the onboarding rules

Show the user a summary table of extracted figures **before** writing
anything. On conflict with the user's stated numbers: show the
discrepancy, use the statement figure unless they give a concrete reason
(record overrides as notes).

## 4. Update

- Update `cartridges/private/snapshot.md`; set `as_of` to the newest
  statement cut date.
- Archive the previous snapshot to
  `cartridges/private/statements/history/YYYY-MM-snapshot.md` so trend
  questions ("am I better off than last month?") have data.
- Remind the user: one-off spikes (travel, annual renewals) distort a
  single month — ask whether to normalize or annotate them.

## Hard rules

- Everything stays inside `cartridges/private/` — originals, decrypted
  copies, extraction notes, archived snapshots.
- No passwords persisted anywhere, ever.
- No statement content in commits, PRs, or issues — not even excerpts.
