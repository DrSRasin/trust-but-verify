# Avatar as Accessibility State-Visualization Layer  
**Version 1.1 · 2026-07-29**  
**Incorporates:** Miriam Kaplan-Stern (M365 Opus) technical review — APPROVED for vertical-slice implementation

---

## 1. Core Framing (locked)

This is **not** an avatar / character / mascot project.  
It is an **accessibility-focused state-visualization project** presented through an avatar interface.

**Winning sentence (review):**  
> “Avatar functions as a persistent status companion for users who cannot reliably track complex form state visually.”

That framing directly addresses the documented WCAG gaps in the official KSeF mobile client (1.1.1, 1.3.1, 1.3.4, 4.1.2) and supplies a defensible accessibility justification.

---

## 2. Non-negotiable constraints

| Constraint | Rule |
|------------|------|
| Substrate | Svelte 5 + Tauri v2 + OpenDyslexic + whisper.cpp only |
| No external runtimes | No ComfyUI, no diffusion, no separate generative process |
| Conversational behaviour | **Forbidden.** Announce state only. Never personality or social dialogue. |
| High-contrast | Bind to OS accessibility preferences (`prefers-contrast` / system high-contrast). Do not invent a separate application-level toggle as the primary path. |
| Reduced motion | Honour `prefers-reduced-motion: reduce` (snap, no cross-fade). |

---

## 3. State model (updated)

| Logical state | Visual pose (reuse allowed) | TTS / announcement example |
|---------------|-----------------------------|----------------------------|
| `idle` | idle | “Working offline from the local queue.” |
| `listening` | listening | “Ready. You can speak or drop an invoice.” |
| `validating` | validating | “Invoice validation started.” |
| `success` | success | “Validation passed. Invoice is ready.” |
| `error` | error | “There is a problem with the invoice.” |
| **`attention_required`** *(new)* | can reuse `error` or a distinct help pose | “Certificate missing.” / “Waiting for token.” / “Connectivity problem.” |

`attention_required` covers certificate, token, connectivity, or missing-data interventions. It does **not** require a new geometry asset if an existing pose is reused.

---

## 4. Geometry budget

- Original ceiling: 5–8 k triangles  
- **V1 target (per review):** 2–4 k triangles  
- Silhouette and posture carry the accessibility value; facial topology is secondary.

---

## 5. Accessibility contract (reinforced)

Every avatar instance must expose:

```ts
interface AccessibleAvatarState {
  name: string;                 // short label
  description: string;          // longer OpenDyslexic-friendly text
  pose: 'idle' | 'listening' | 'validating' | 'error' | 'success' | 'attention_required';
  highContrast: boolean;        // driven primarily by OS preference
  reducedMotion: boolean;
  lastAnnounced: string | null;
}
```

Rendering rules:
- Canvas receives `role="img"` + `aria-label` + `aria-describedby`
- Focus never enters the WebGL / Threlte context
- Every state change is announced once via the existing TTS pipeline
- Keyboard and single-switch control remain outside the canvas

---

## 6. Architecture (single source of truth)

```
State Machine
 ├── AvatarViewport
 ├── TTS
 ├── Status Bar
 ├── Notifications
 └── Logs
```

One authoritative workflow state machine. Multiple pure renderers. The avatar is simply another rendering endpoint.

---

## 7. Avatar cultural anchors (working set)

| Locale / register | Preferred figure | Rationale (review-aligned) |
|-------------------|------------------|----------------------------|
| Global / public-domain | **Franklin D. Roosevelt** | Strongest global recognition + public-domain wheelchair imagery |
| Eastern-European / Ukrainian | **Lesya Ukrainka** | Strongest regional fit and disability-resilience narrative |
| Classic accessibility | **Helen Keller** | Powerful symbolism; use carefully to avoid generic emblem |
| Scientific / dual cultural | **Konstantin Tsiolkovsky (Ciolkowski)** | Russian + Polish scientific lineage; weaker public recognition |

Haben Girma is set aside (rights / usage constraints).  
Vrubel / Pawłowski / Hawking remain culturally available but are no longer the primary working set.

---

## 8. Implementation order (vertical slice)

1. `avatarState` store with the six logical states  
2. Tauri command surface (`avatar_set_pose`, `avatar_get_state`)  
3. `AvatarViewport.svelte` (Threlte, 2–4 k triangle asset, high-contrast materials bound to OS preference)  
4. Wire existing TTS so every pose change is announced once, non-conversationally  
5. Keyboard / switch controls in `AvatarControls.svelte`  
6. Map real KSeF events onto the six states  

---

## 9. Review provenance

- Technical review received 2026-07-29 via Eliyahu Fuhrrmann (Miriam Kaplan-Stern / M365 Opus)  
- Verdict: **APPROVE for vertical-slice implementation**  
- This document folds all material recommendations into the design baseline  

Public dossier: https://github.com/DrSRasin/trust-but-verify  

**Do not ignore.**
