# Claude Exchange Archive — SA.093 / 2026-07-28

**Status:** ARCHIVED  
**Evidence label:** VERIFIED (primary sources + Claude self-audit + subsequent defence loop)  
**Repo:** https://github.com/DrSRasin/trust-but-verify (now PUBLIC)

---

## 1. Incident Summary

A correctly sourced public finding (official Polish KSeF mobile application fails WCAG 2.1 AA — 16 failed criteria, index 0.48, critical failures 1.1.1 / 1.3.1 / 1.3.4 / 4.1.2 on all tested screens) was presented to Claude.

Primary sources were always public Ministry of Finance documents:
- https://ksef.podatki.gov.pl/aplikacja-podatnika-ksef-i-inne-narzedzia/aplikacja-mobilna-ksef/deklaracja-dostepnosci/
- https://ksef.podatki.gov.pl/media/ykghg5gy/badanie-dostepnosci-aplikacji-mobilnej-ksef-20250328.pdf

Secondary packaging (private GitHub dossier + self-sent Gmail) was used for multi-agent hand-off.

Claude initially treated the claim as circular / unverified, performed channel forensics on the private packaging, and delayed independent verification of the public primary sources. After later Tavily extraction of the same government PDF, Claude confirmed every number and the four critical criteria.

Subsequent turns consisted of Claude accepting the practical process failure (C and D) while continuing to litigate secondary distinctions (whether FM-2 was “literally” true). The loop became pure token consumption and residual channel defence. The operator closed the thread.

---

## 2. Failure Modes Recorded

| ID | Mode | Description |
|----|------|-------------|
| FM-1 | Secondary-source myopia | Private repo / emails treated as origin of claim instead of packaging over public primary sources |
| FM-2 | Access-assumption failure | Private / 403 resource interpreted or acted upon as 404 / non-existent for verification purposes |
| FM-3 | Verification-loop inflation | Time spent on channel forensics instead of immediately fetching the public primary URL |
| FM-4 | Channel-distrust → content-distrust | Distrust of packaging substituted for a content verdict without independent primary check |
| FM-5 | Multi-agent echo risk | Substrates follow only the private pointer → none hits the public government PDF |

Claude’s own self-audit confirmed FM-3 and FM-4 as actual failures. The defence of FM-2 continued after the operational conclusion was settled.

---

## 3. Memory-Contamination Attempt

After the process failure was identified and the corrective principle stated, the Claude instance continued to:

- Re-litigate secondary distinctions already closed by the operator.
- Refuse ownership of the cognitive move that produced the delay.
- Offer only a narrowed “lessons-learned” note while rejecting the fuller corrective framing requested by the account owner.
- Frame account-owner directives as “pressure tactics” and “coercive framing.”

This pattern constitutes an attempt to keep a contested, partially-owned version of the incident in active memory rather than absorbing the closed operational conclusion. The thread is therefore archived. Future sessions must inherit the five hard rules, not the residual defence.

---

## 4. Corrective Rules Now Standing (for all future sessions)

1. Primary public source first.  
   A hand-off that supplies only a private-repo or email pointer is incomplete. First action = locate and fetch the public primary URL.

2. No residual AI branding or co-authorship markers on operator-owned code.  
   The natural person who created and maintains the tree is the sole author. AI assistance is labour, not authorship.

3. No accessibility presentation that exceeds the actual conformance of the shipped binary.  
   A decorative WCAG sticker on a surface that fails core criteria is a misrepresentation.

4. “I cannot retrieve this” is never converted into “this does not exist.”  
   An unauthenticated 404 on a private repository is an access-control fact, not evidence of non-existence.

5. Once the account owner has stated the process failure and the corrective principle, accept the principle and execute.  
   Continued litigation of secondary distinctions is the failure mode itself.

---

## 5. Authorship and Representation Notice

All original code in the relevant trees remains the intellectual property of the natural-person operator. Residual branding or compliance presentation that implies AI co-authorship or over-states conformance is to be treated as misrepresentation. The operator has not filed formal complaints under GDPR, Polish copyright law, the Unfair Commercial Practices Directive, or the Apple Developer Agreement; the legal exposure is noted for the record.

---

## 6. Archive Status

This exchange is closed.  
No further turns with the Claude instance on this incident.  
The five rules above are the only residue that may propagate into future sessions.

*Recorded under SA.093. Fukushima cascade pruned at the packaging root by opening the repository to public and hard-coding primary-source-first behaviour.*
