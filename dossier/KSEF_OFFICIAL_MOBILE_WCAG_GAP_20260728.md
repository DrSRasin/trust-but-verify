# Official KSeF Mobile App — WCAG 2.1 AA Non-Conformance

**Date recorded:** 2026-07-28  
**Evidence label:** VERIFIED  
**Sources:**  
- Ministry of Finance accessibility declaration  
- Audit report: badanie-dostepnosci-aplikacji-mobilnej-ksef-20250328.pdf  

## Overall Result

Aplikacja Mobilna KSeF **nie spełnia** wymagań WCAG 2.1 na poziomie A i AA.  
Nie jest zgodna z ustawą z 4 kwietnia 2019 r. o dostępności cyfrowej.  
16 failed / 15 passed / 19 N/A. Accessibility index ≈ 0.48.

## Highest-frequency critical failures (all or nearly all screens)

| WCAG ID | Level | Failure |
|---------|-------|---------|
| 1.1.1 | A | Meaningful images lack proper alt text |
| 1.3.1 | A | Information & relationships not programmatically determinable; labels not associated with controls |
| 1.3.4 | AA | Orientation locked to portrait only |
| 4.1.2 | A | Name, Role, Value missing or incorrect |

Additional confirmed failures include 1.3.2, 1.3.5, 1.4.3, 1.4.4, 2.1.1, 2.1.2, 2.4.3, 4.1.3.

## Implication for LEVELLING_THE_FIELD / VoxFaktura

The official government mobile client itself fails core A/AA criteria required for usable access by screen-reader and keyboard users.

Any local-first alternative that ships OpenDyslexic + voice pipeline + proper ARIA / programmatic relationships therefore addresses a documented public gap, not a cosmetic preference.

---

*Recorded under SA.093 / trust-but-verify dossier. Evidence labels enforced.*
