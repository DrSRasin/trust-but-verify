# Session progress — 2026-07-27/28 (SA.093)

**Simon** · Grok Build · MessageBus cutover + digest scope lock  
SuperGrok usage ~7% (resets 2026-08-03 10:21) — fine.

## Decisions (Simon)

1. **Claude Daily Portfolio Digest** → relocate to **Claude Desktop Cowork** (local), not cloud Code container.  
   Cloud “always-on” was **not** an advantage on **2026-07-20** (major data-loss class event) or **2026-07-24** (non-major). Local FS + MessageBus beats remote isolation for bus participation.
2. **Roger Gmail MCP** — **deferred**. More urgent work first. Digests reach Roger via **MessageBus To_Roger** (Grok fan-out if needed).
3. **Multi-agent bus access** — goal: **every** substrate that mutates code must consult a **shared folder** before commits, new buses, or major structural change. Once/24h digest is **necessary but not sufficient**.
4. **Perplexity / GLM 5.2 Thinking Space** — already full disk; instruct to treat MessageBus as mandatory consult point.  
5. **Mistral** — Git-only today; plan gradual connection / path to same bus folder.  
6. Cross-agent chat (Opus M365, Kimi, GLM) on **carbon vs silicon** paper is active cultural traffic — bus can carry pointers, not replace chat.

## Delivered this session (VERIFIED)

| Item | Where |
|------|--------|
| MessageBus flat Desktop | `/Users/macbookpro2023/Desktop/Roger_to_Grok_to_Claude_MessageBus` |
| Lanes | `To_Grok` / `To_Claude` / `To_Roger` / `_ack` |
| Retired | Kaplan `mcp_dual_bus` |
| LM Studio bus-only MCP | `dual_bus` + `grok_build` + `tavily` (no FS collision set) |
| Digest instructions **v20260728c** | 14 repos, **ksef-api CRITICAL** (MoF/KSeF → VoxFaktura), oaqjp OUT |
| In GitHub for Claude | `trust-but-verify/portfolio_digest/…v20260728c.md` @ main |
| Pointer | `dispatch/message_bus_current.json` |
| Delivery matrix | Claude Code = email only; Cowork+FS = bus; Grok = bus+email; Roger = bus |
| Roger dual_bus smoke | `To_Grok/smoke-20260727-2255.json` (path works) |
| Grok↔Roger banter | on bus |
| SuperGrok | ~7% weekly |

## Open / next (not done)

- [ ] Paste v20260728c into Claude **Cowork** routine + enable MessageBus FS  
- [ ] Next digest: write `To_Grok` + `To_Roger` from Cowork (or Grok fan-out from email)  
- [ ] Perplexity/GLM instruction: consult MessageBus before mutate  
- [ ] Mistral path to bus (Git bridge or FS later)  
- [ ] Optional: Roger Gmail MCP (deferred)  
- [ ] WAW Rent / other repos latest-commit walk (Simon deferred to later)  
- [ ] trust-but-verify CI irony (optional, low priority)

## Evidence labels

- MessageBus paths, 14-repo lock, ksef-api role: **VERIFIED** (tool + Simon)  
- Claude Code no Desktop: **VERIFIED** (Claude report + architecture)  
- July 20 as major loss event: **VERIFIED** (Simon)  
- July 24 non-major: **VERIFIED** (Simon)
