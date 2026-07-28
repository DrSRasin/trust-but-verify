# trust-but-verify

> доверяй и проверяй · 信任并验证

MnemAxis dispatch + pointer infrastructure — AI harness status, anti-amnesia, and **where the live message bus actually is**.

**Operator:** Dr. Simon Rasin MD MPH PhD (address as **Simon**)  
**Doctrine:** LEVELLING_THE_FIELD · KAPLAN_CODE_SPACE  
**Session anchor:** SA.093 · 2026-07-28

---

## CRITICAL NEW DOSSIER (2026-07-28)

**Official KSeF Mobile App fails WCAG 2.1 AA.**  
Full report: `dossier/KSEF_WCAG_FULL_REPORT_20260728.md`  
(also local PDF in artifacts)

Implication: any local-first OpenDyslexic + voice + ARIA surface (VoxFaktura / LogoSoma) addresses a documented public gap, not a cosmetic preference. End-users include fringe / abandoned immigrant operators who cannot rely on the government client.

---

## LIVE MESSAGE BUS (read this first — not under dispatch/nodes)

Async multi-agent **TALK** is **not** inside `dispatch/nodes/*.json`.

| What | Path |
|------|------|
| **Bus root** | `/Users/macbookpro2023/Desktop/Roger_to_Grok_to_Claude_MessageBus` |
| Grok inbox | `…/To_Grok/` |
| Claude inbox | `…/To_Claude/` |
| Roger inbox | `…/To_Roger/` |
| Acks | `…/_ack/` |

**Canonical pointer in this repo:**  
`dispatch/message_bus_current.json` ← open this for current scope, digest instructions, and bus paths.

**Retired bus:**  
`Desktop/Kaplan_Warroom/06_Session_Handoff_Infra/mcp_dual_bus` (do not write new packets there).

### TALK vs HIRE
- **TALK** (message / digest / ack) → write JSON under MessageBus lanes above  
- **HIRE** (run code) → grok_build / coding agents — not the bus  

### Daily Portfolio Evidence Digest
- Instruction file **v20260728c** (scope **14**, including **ksef-api** critical):
  - `Desktop/Kaplan_Warroom/06_Session_Handoff_Infra/CLAUDE_DAILY_PORTFOLIO_DIGEST_INSTRUCTIONS_v20260728.md`
  - also copied at MessageBus root for Claude Desktop  
- After each digest: **email Simon** + write  
  `To_Grok/msg-portfolio-digest-YYYYMMDD.json` and  
  `To_Roger/msg-portfolio-digest-YYYYMMDD.json`  
- **ksef-api** = Polish MoF / KSeF protocol watch → feeds **VoxFaktura** when Simon GO’s.  
  Use direct `DrSRasin/ksef-api` if `search_repositories` returns 0.

---

## Purpose of this repo

Prevent the failure mode where an AI substrate finishes work with no durable status, and the next session opens blind.

- `dispatch/` = node check-ins + status log (still valid for check-in protocol)  
- MessageBus on Desktop = actual async envelopes between Claude / Grok / Roger  

---

## Folder Structure

```
trust-but-verify/
├── dispatch/
│   ├── message_bus_current.json  ← LIVE bus + digest scope pointer (READ FIRST)
│   ├── status_current.json
│   ├── dispatch_log.jsonl
│   ├── schema/checkin_v1.schema.json
│   └── nodes/   ← per-substrate check-in (not the message bus)
├── dossier/
│   ├── KSEF_OFFICIAL_MOBILE_WCAG_GAP_20260728.md
│   └── KSEF_WCAG_FULL_REPORT_20260728.md
├── protocol/
├── hangovers/
└── README.md
```

---

## Dispatch Check-In Rule

Every substrate should emit a check-in at session open / major change / session close.  
Append to `dispatch/dispatch_log.jsonl`. Never overwrite history.

Also: for **messages**, use MessageBus lanes — do not invent paths under `dispatch/`.

---

## Evidence Labels

| Label | Meaning |
|---|---|
| VERIFIED | Confirmed by Simon or direct tool output |
| INFERRED | Reasonable conclusion from available evidence |
| SPECULATIVE | Plausible but unconfirmed — must be labeled |
| UNRESOLVED | Requires HITL before proceeding |

---

*The bench holds. The CLAW holds. Emet.*
