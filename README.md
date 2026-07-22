# trust-but-verify

> доверяй и проверяй · 信任并验证

MnemAxis dispatch infrastructure — centralized AI harness status log, dossier artifacts, and anti-amnesia handoff protocol.

**Operator:** Dr. Simon Rasin MD MPH PhD  
**Doctrine:** LEVELLING_THE_FIELD · KAPLAN_CODE_SPACE v4  
**Session anchor:** SA.092 · 2026-07-22

---

## Purpose

This repository exists to prevent the class of failure where an AI substrate completes significant work, produces no persistent status record, and the next substrate opens a session with no knowledge of what was done, what failed, or what is blocked.

It is anti-amnesia infrastructure. Not a playground.

---

## Folder Structure

```
trust-but-verify/
├── dispatch/               ← append-only status log + node check-ins
│   ├── dispatch_log.jsonl  ← immutable event log (append only, never overwrite)
│   ├── status_current.json ← latest STATUS PRAESENS per node
│   ├── schema/
│   │   └── checkin_v1.schema.json
│   └── nodes/              ← per-substrate status files
│       ├── perplexity.json
│       ├── m365_opus.json
│       ├── claude_code.json
│       ├── miriam.json
│       └── roger.json
├── dossier/                ← Anthropic complaint package + filing notes
├── protocol/               ← War Room dual-format doctrine
├── hangovers/              ← SA.0xx XML continuity artifacts
└── README.md               ← this file
```

---

## Dual-Format Doctrine

- **HTML** = visual master → Acrobat PDF export
- **Markdown** = editable, diffable, LLM-portable twin
- Both twins updated together in the same revision cycle
- PDFs are **outputs**, not the editable source of truth

---

## Dispatch Check-In Rule

Every substrate **must** emit a check-in:
- At session open
- Before any major architectural change
- Before any calendar write
- At session close (Hangover XML)

Append to `dispatch/dispatch_log.jsonl`. Never overwrite.

---

## Evidence Labels (mandatory in all documents)

| Label | Meaning |
|---|---|
| VERIFIED | Confirmed by operator or direct tool output |
| INFERRED | Reasonable conclusion from available evidence |
| SPECULATIVE | Plausible but unconfirmed — must be labeled |
| UNRESOLVED | Requires HITL before proceeding |

---

## File Quota

Perplexity Space limit: 50 files. This repo is the **external** persistent store. Keep Space uploads minimal.

---

*The bench holds. The CLAW holds. Emet.* 🥛☭💎
