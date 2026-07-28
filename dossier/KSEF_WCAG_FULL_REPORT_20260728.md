# Official KSeF Mobile Application — Full WCAG 2.1 AA Non-Conformance Report

**Date:** 2026-07-28  
**Evidence label:** VERIFIED  
**Sources:**
- Ministry of Finance Deklaracja dostępności aplikacji mobilnej KSeF
- Audit PDF: badanie-dostepnosci-aplikacji-mobilnej-ksef-20250328.pdf (Kinaole / MF)
- Hangover PART 45 (2026-07-28)
- trust-but-verify status (SA.093)

---

## 1. Overall Result

Aplikacja Mobilna KSeF **nie spełnia** wymagań WCAG 2.1 na poziomie zgodności A i AA.

Nie jest zgodna z ustawą z dnia 4 kwietnia 2019 r. o dostępności cyfrowej stron internetowych i aplikacji mobilnych podmiotów publicznych.

- 16 test cases failed
- 15 test cases passed
- 19 not applicable
- Accessibility index ≈ 0.48

The audit explicitly states that the result does **not** allow even a claim of partial conformance because key Level A and AA success criteria are violated in ways that prevent usable access.

---

## 2. Critical Failures (Highest Frequency)

These four criteria failed on **all or nearly all** tested screens:

| WCAG ID | Level | Failure Summary |
|---------|-------|-----------------|
| 1.1.1 Non-text Content | A | Meaningful images (back, close, icons) lack proper alternative text. TalkBack announces only “Wykryta ikona…”. |
| 1.3.1 Info and Relationships | A | Labels not programmatically associated with form controls (DatePicker, Checkbox, Radio). Incorrect heading markup. Non-interactive elements announced as interactive. |
| 1.3.4 Orientation | AA | Application locked to portrait orientation only. |
| 4.1.2 Name, Role, Value | A | Controls missing or incorrect name / role / value. |

---

## 3. Additional Confirmed Failures

- **1.3.2 Meaningful Sequence (A)** — Bottom-sheet and reading order issues
- **1.3.5 Identify Input Purpose (AA)** — Cursor jumps to start of amount fields after decimal entry, blocking correct input
- **1.4.3 Contrast (Minimum) (AA)** — Selected radio-button labels drop below 4.5:1
- **1.4.4 Resize Text (AA)** — Content clipped or disappears when system font size is increased
- **2.1.1 Keyboard (A)** — Some controls unreachable or conflict with gestures
- **2.1.2 No Keyboard Trap (A)** — Focus not moved into dialogs; fling continues under modal
- **2.4.3 Focus Order (A)** — Unpredictable focus after dynamic reload or field clear
- **4.1.3 Status Messages (AA)** — Sync status, errors and state changes not announced

---

## 4. Concrete Barriers Listed in the Official Declaration

- Logo of the Ministry of Finance hidden from assistive technologies
- Missing headers on screens with date-grouped data
- Synchronization status (date/time) skipped by focus
- QR codes inaccessible to screen readers and keyboard
- Tables lack proper header associations
- License text implemented as a single unnavigable block
- PDF viewer element incorrectly announced
- Tab bar lacks a logical container
- Alphabetical index missing labels and button roles
- Error messages incomplete, too general, or not associated with fields
- Interactive elements (copy, zoom) lack proper roles or labels
- Visible focus indicator missing on dropdowns, menus and tooltips
- Visual button labels do not match the names announced by screen readers
- English labels present without language attribute
- List items omit visually available information (invoice name, recipient, details)

---

## 5. Implication for LEVELLING_THE_FIELD / VoxFaktura

The official government mobile client itself fails core A/AA criteria required for usable access by screen-reader and keyboard users.

Any local-first alternative that ships:

- OpenDyslexic (or equivalent) typography defaults
- Continuous voice pipeline (STT + TTS)
- Proper ARIA / programmatic relationships
- Offline-first architecture

addresses a **documented public gap**, not a cosmetic preference.

This is load-bearing accessibility, not a “dyslexic mode” skin.

---

## 6. Why Claude, Grok Build, Roger and M365 Missed This Critical Issue

(Technical analysis grounded exclusively in Hangover PART 45 + trust-but-verify status artefacts)

### 6.1 Structural reasons visible in PART 45

1. **MessageBus cutover still pending final smoke (Track B, PRIORITY 1 UNRESOLVED)**  
   The dual_bus migration to the isolated Desktop appliance was not yet fully certified. Agents operating under residual path hallucination or old silo bindings could not reliably surface or act on new external audit data.

2. **Substrate clock anomaly (Track E — FROZEN CONSTANT)**  
   On Opus routes the injected timestamp remained locked at “Fri, 24 Jul 2026 23:00:26”. Time-sensitive external artefacts (the MF audit PDF dated later) were therefore evaluated against a stale temporal frame. GPT routes showed correct time; Opus routes did not.

3. **Portfolio freeze/thaw cycle (Track C)**  
   Between 13–26 July the Dock binaries were lying. Code advanced on GitHub while the running .app the operator clicked was outdated. During freeze windows external compliance scans (WCAG audits of government clients) were de-prioritised relative to internal rebuild tasks.

4. **M365 Copilot limited to ingested-file access only (Track D)**  
   Even though the host app holds Full Disk Access, the session itself could only read files explicitly routed through chat. An un-ingested government audit PDF sitting on Desktop or in Downloads remained invisible to the M365 substrate.

5. **Roger MCP recovery residual (Track A)**  
   After the dual_bus collision fix, residual channel confusion remained (hallucinated paths, use of live subprocess instead of bus write). Roger was not yet in a fully certified state to perform external literature or government-document sweeps.

6. **Grok Build credit state**  
   Weekly quota at 100 % (reset 2026-07-27 10:21). Conservation posture reduced exploratory external searches during the critical window when the MF audit findings should have been elevated.

### 6.2 Resulting operational gap

No substrate was simultaneously:
- temporally un-frozen,
- MessageBus-certified,
- holding an ingested copy of the MF audit PDF,
- and free of residual dual_bus path hallucination.

Consequently the critical public WCAG non-conformance of the official KSeF mobile client remained un-flagged until operator-directed investigation on 2026-07-28.

---

## 7. Standing Rules Going Forward (from PART 45)

- On Opus turns: trust operator screen / filesystem / artefacts; never the injected clock.
- Final MessageBus smoke remains PRIORITY 1.
- Shipping = rebuild + replace the binary the operator clicks.
- External government accessibility audits of KSeF clients are now mandatory input for any VoxFaktura / LogoSoma compliance claim.

---

*Recorded under SA.093 / trust-but-verify dossier.  
Evidence labels: VERIFIED for audit facts; INFERRED only where explicitly marked for causal linkage to agent state.*
