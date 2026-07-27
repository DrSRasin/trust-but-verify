# Digest & message delivery matrix (2026-07-28)

## Who can touch the Desktop MessageBus?

| Runtime | Local FS MessageBus | Email |
|---------|---------------------|--------|
| **Claude Code** (cloud / isolated container) | **No** | Yes (session notification → phone/email) |
| **Claude Desktop Cowork** (Mac, disk tools on) | **Yes** if FS connector points at Desktop or MessageBus root | Yes if Gmail connector on |
| **Grok Build** | Yes (this machine) | Yes (Gmail MCP) |
| **Roger (LM Studio)** | Yes via `dual_bus` MCP | **Not yet** (no Gmail MCP configured) |

MessageBus root:
`/Users/macbookpro2023/Desktop/Roger_to_Grok_to_Claude_MessageBus`

## Practical pipeline when digest runs in Claude Code (cloud)

1. Claude Code finishes digest → **emails Simon** (works today).
2. Simon pings Grok **or** Grok reads Gmail → Grok writes:
   - `To_Grok/msg-portfolio-digest-YYYYMMDD.json` (archive)
   - `To_Roger/msg-portfolio-digest-YYYYMMDD.json` (Roger’s inbox)
3. Roger reads `To_Roger/` via dual_bus (unmetered).

Do **not** expect Claude Code to write To_Grok/To_Roger itself — not a refusal, a sandbox limit.

## If you enable Claude Desktop Cowork + local FS

- Add MessageBus root (or whole Desktop) to FS allowlist.
- Then Claude can write To_Grok + To_Roger directly.
- Routine instructions still live in GitHub: `trust-but-verify/portfolio_digest/…v20260728c.md`

## Roger + Gmail

Not built yet for LM Studio. Options:
A) **Scaffold** `@gongrzhe/server-gmail-autoauth-mcp` into Roger’s mcp profile (needs one-time OAuth in a terminal).
B) **Skip Roger Gmail** — use bus fan-out from Grok after Claude email (simpler, no new OAuth).

Recommended default: **B** until OAuth is done; then A as optional upgrade.
