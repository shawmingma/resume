# Final Revision Report — Cryogenic Reliability in HfO₂ FeFETs (IEEE TMAT)

Date: 2026-10-17  
Detailed item-by-item list: [`MANUSCRIPT_CORRECTIONS.txt`](MANUSCRIPT_CORRECTIONS.txt)

## 1. Status at a glance

| Area | Critical | Major | Minor |
|---|---|---|---|
| Build / cross-file consistency | 9 | 2 | – |
| Introduction | – | 3 | 3 |
| Results | 3 | 6 | 15 |
| Discussion | 3 | – | 1 |
| Conclusion | – | 1 | 2 |
| Methods | 2 | 6 | 5 |
| Supplementary | 4 | – | 4 |
| 08_image.tex | 1 | – | – |
| reference.bib | 4 | 2 | 6 |
| New data / text required | – | 8 | – |

**The source will not compile as-is** (bib syntax errors, duplicate labels, subfig+subcaption clash). Fix §0 first.

## 2. Where changes are REQUIRED (must do before resubmission)

### A. Build blockers
1. `reference.bib`: broken `PyMatching` entry, stray `}` after `suman2`, duplicate key `parmar2023demonstration`.
2. Remove `08_image.tex` (obsolete duplicate of all main-text figures; still contains Fig 4(i,j) that Reviewer 1 asked to delete).
3. Duplicate labels `fig:S1` (Methods + Supplementary) and `fig:S2` (used for S2 and S3).
4. Choose `subfig` **or** `subcaption`, not both.

### B. Factual / internal contradictions a reviewer will catch
| Item | File(s) | Fix |
|---|---|---|
| SiO₂ IL thickness 1.2 nm vs 0.85 nm | Methods / Suppl. S1 | use TEM value everywhere |
| Cryo C–V 1 kHz vs 100 kHz | Methods / Results §C | pick one; add to every C–V caption |
| Fig 1(d) "−3 V" but panel shows +3 V; captions (d),(f) call I_nsw "I_sw" | Results | fix sign and labels; name conduction mechanism |
| "MW > 1 V at ±7 V/50 µs" — no such data point | Results | ±6 V/50 µs or ±7 V/20 µs |
| Table I cites [39] — not in bib | Discussion | it is Hur 2021 (`CryoShimeng`); use `\cite{}` keys |
| Fig 7 trapped-charge polarity reversed | fig7.pdf | electrons for +5 V state, holes for −5 V state |
| "TaN = titanium nitride" | Abstract | tantalum nitride |
| Broken sentence "polarization-to-channel Cooling to 10 K" | Discussion | insert "coupling." |
| "activate The implanted dopants…" | Methods | grammar |
| RT MW "merges at 10⁴" — figure says 10⁵ | Results | 10⁵ |
| ±7 V/1 µs data promised in Abstract/Table I but never cited | Results, Conclusion | reference Supplementary Fig S3 |
| Pristine 10 K MW 1.15 V (Fig 3e) vs 2.3 V (Fig 4b) | Results | explain device/geometry difference |
| Duplicate bib papers: FeFET3=de2022demonstration, FeFET4=de202228, 10122209=ma20232, Lederer_model=lederer2023spice, EDL4=cho2024exploring, 80=EDL1 | bib | merge |
| `agarwal2025` title renders "¿10 cycles"; `LFN5` author "Fleetwood and D., M." | bib | fix |

### C. Reviewer requests still unanswered (need new data or text)
| Reviewer item | What to add | Where |
|---|---|---|
| Editor M2 / R1 #13 | readout delay after last pulse, interruption duration, C–V sweep sequence, PUND inter-pulse delays | Methods + Fig S1(b) |
| Editor M5 | why 10 K; no data below 10 K; relevance to 4 K systems | Intro or Methods |
| Editor M6 | N devices, variability / error bars | Methods, Fig 3(e), Fig 4(b) |
| Editor M4 | quantitative trapped-charge estimate ΔN_t = C_g·ΔV_th/(q·A_G); give A_G | Results §C |
| Editor m5 | numbers for "substantially reduced leakage", "nearly unchanged", "comparatively stable" | Results captions/text |
| Editor m8 | shorten Fig 4, 5, 7 captions to data + conditions | Results, Discussion |
| R1 #2, #12 | overlay RT vs 10 K: V_th–cycles, P–V, C–V on same axes | new figure |
| R1 #3 | explain V_c asymmetry (−4 V vs +2.5 V) | Results |
| R1 #4 | state explicitly: V_th,HVT shifts ~2 V while I_sw peaks shift <0.3 V | Results |
| R1 #5 | plot LVT and HVT separately in Fig 3(e) | Fig 3 |
| R1 #7 | retention (LVT/HVT, RT & 10 K); PUND timing; ±6 V PUND at 10⁶ to exclude imprint | new data |
| R1 #14 | justify keeping Figs 5 & 7 by tying C–V inversion to Fig 4(b) timing | Discussion |
| R1 #1 | float placement so figures sit near discussion | all |

## 3. Already resolved in this revision (no action)
- R1 #8 band-gap values (5.6 / 9.3 eV) and large-signal capacitance text (cites Agarwal TED 2024).
- R1 #9 Fig 4(i,j) removed from `02_Results.tex` (but still in `08_image.tex` → delete that file).
- R1 #10 sentence corrected.
- R1 #11 dopant freeze-out reassessed (S/D degenerate, slow p-body holes).
- Editor M1 comparison table added (needs MW + mechanism columns and bib keys).
- ±7 V/1 µs data exists as Supplementary Fig S3.

## 4. Recommended order of work
1. §0 build blockers (30 min).
2. §B contradictions (1–2 h, mostly text).
3. Bib clean-up (1 h).
4. Methods additions: timing, N, A_G, V_th criterion, RTA, why 10 K (1 h).
5. New measurements: retention + PUND delay + overlays (lab time).
6. Fig 7 redraw; caption trimming; abstract rewrite.
7. Point-by-point response letter.
