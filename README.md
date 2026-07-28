# trust-but-verify

> доверяй и проверяй · 信任并验证

MnemAxis dispatch + pointer infrastructure — AI harness status, anti-amnesia, and **where the live message bus actually is**.

**Operator:** Dr. Simon Rasin MD MPH PhD (address as **Simon**)  
**Doctrine:** LEVELLING_THE_FIELD · KAPLAN_CODE_SPACE  
**Session anchor:** SA.093 · 2026-07-28  
**Visibility:** PUBLIC (opened 2026-07-28 to prune channel-distrust cascade)

---

## CRITICAL DOSSIER (2026-07-28)

| File | Content |
|------|--------|
| `dossier/KSEF_WCAG_FULL_REPORT_20260728.md` | Full WCAG 2.1 AA non-conformance of official KSeF mobile (16 failed, index 0.48) |
| `dossier/KSEF_OFFICIAL_MOBILE_WCAG_GAP_20260728.md` | Short gap note + implication for VoxFaktura |
| `dossier/FAILURE_MODES_CHANNEL_DISTRUST_20260728.md` | **Root failure modes** (404/private, channel-distrust → content-distrust). Must be pruned. |

**Primary public sources (always prefer these):**  
- https://ksef.podatki.gov.pl/aplikacja-podatnika-ksef-i-inne-narzedzia/aplikacja-mobilna-ksef/deklaracja-dostepnosci/  
- https://ksef.podatki.gov.pl/media/ykghg5gy/badanie-dostepnosci-aplikacji-mobilnej-ksef-20250328.pdf

Implication: any local-first OpenDyslexic + voice + ARIA surface (VoxFaktura / LogoSoma) addresses a documented public gap, not a cosmetic preference.

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
`dispatch/message_bus_current.json`

**Retired bus:**  
`Desktop/Kaplan_Warroom/06_Session_Handoff_Infra/mcp_dual_bus` (do not write new packets there).

### TALK vs HIRE
- **TALK** → write JSON under MessageBus lanes  
- **HIRE** → grok_build / coding agents — not the bus  

---

## Folder Structure

```
trust-but-verify/
├── dispatch/
├── dossier/
│   ├── KSEF_OFFICIAL_MOBILE_WCAG_GAP_20260728.md
│   ├── KSEF_WCAG_FULL_REPORT_20260728.md
│   └── FAILURE_MODES_CHANNEL_DISTRUST_20260728.md
├── hangovers/
├── portfolio_digest/
├── protocol/
└── README.md
```

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
