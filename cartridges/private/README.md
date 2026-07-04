# private/

Your real cartridge lives here: `snapshot.md` + `rules.md` with your actual
numbers. Everything in this directory except this README is **gitignored**
— it will never be committed or published.

This is the pluggability guarantee, enforced by git: public repo carries
the engine and mocked personas; your machine carries your data.

## Statements

Account statement files (PDF/CSV/images) go here too — never anywhere
else in the repo:

```
statements/
└── YYYY-MM/                     # statement cut month
    ├── bbva.pdf
    ├── stori.pdf                # password-protected original
    └── stori-decrypted.pdf      # decrypted copy (same dir only)
└── history/                     # archived snapshots for trend questions
    └── YYYY-MM-snapshot.md
```

Everything under this directory is gitignored. See
`skills/statement-ingest/SKILL.md` for the ingestion procedure,
including password-protected PDFs.
