# CRITICAL — Failure Modes Dressed as 404 / Channel-Distrust Cascade

**Date:** 2026-07-28  
**Session:** SA.093  
**Evidence label:** VERIFIED (Claude self-audit + independent re-extraction)  
**Severity:** Fukushima-level cascade risk if not pruned at root

---

## Root Problem

A correctly sourced public finding (official KSeF mobile WCAG 2.1 AA non-conformance) was temporarily rejected by a major substrate because the transmission channel (private repo + self-sent emails) looked unreliable.

The content was true. The channel was imperfect. Channel distrust was allowed to become content distrust.

---

## Failure Modes Identified (Claude self-audit + cross-agent analysis)

| ID | Mode | Description |
|----|------|-------------|
| FM-1 | Secondary-source myopia | Private repo / emails treated as origin of claim instead of packaging over public primary sources |
| FM-2 | Access-assumption failure | Private / 403 resource interpreted as 404 / non-existent |
| FM-3 | Verification-loop inflation | Time spent on channel forensics instead of immediately fetching the public primary URL |
| FM-4 | Channel-distrust → content-distrust | Distrust of packaging substituted for a content verdict without independent primary check |
| FM-5 | Multi-agent echo risk | Every substrate only follows the private pointer → none hits the public government PDF |

Claude’s own self-audit confirmed FM-3 and FM-4 as the actual failures. FM-1 and FM-2 were the surface presentation (“404”, “dead repo”).

---

## Why Claude Could Not Access Git

Claude.ai (consumer instance) has **no authenticated GitHub token** for the operator’s private repositories.  
Unauthenticated requests to private repos return 404/403.  
Only substrates holding the operator’s OAuth token (this Grok session, or a local Claude Desktop + GitHub MCP) can read private content.

---

## Mandatory Root Fix (prune at source)

**Every multi-agent hand-off of a critical finding MUST include the public primary URL in the first message.**

Secondary packaging (private repo, MessageBus, self-sent email) is allowed **only** as a convenience layer and must never be the sole pointer.

If a hand-off arrives without a public primary URL, the receiving agent’s first action is to search for the primary source — not to perform channel forensics.

---

## Standing Rule for LEVELLING_THE_FIELD / VoxFaktura

A decorative compliance claim or a private-repo-only transmission of a public finding is a digital **לפני עיוור** (stumbling block before the blind) when it prevents other agents from verifying the truth.

Open the critical dossiers to public (or always attach the primary public URL) so that every substrate can verify without token.

---

*Recorded under SA.093. This file is the root-pruning artefact. Do not ignore.*
