# PHYSIS

**Pediatric Height Yielded through Skeletal Interpretation System**

Pediatric endocrine clinical decision support — bone age scoring, adult height prediction, growth charting, and additional calculators for inpatient and outpatient practice. PHYSIS is a **standalone application built from scratch** for pediatric endocrinology workflows. 

**Inspiration**

PHYSIS draws on published methods and clinical references with its main focus of making important clinical tools available and easily accessible. While entirely developed by myself, PHYSIS takes inspiration from [Bone Age](https://play.google.com/store/apps/details?id=uk.co.eatyourpeas.tannerwhitehouse) and [endocrinologist](https://github.com/eatyourpeas/endocrinologist), both developed by [eatyourpeas](https://github.com/eatyourpeas). Inspiration for additional clinical tools from [Child Metrics](https://www.ceddcozum.com/), developed and maintained by the Turkish Society for Pediatric Endocrinology and Diabetes (TSPED).

**Disclaimer**

Please be sure to read the [Disclaimer](https://physiscalcs.dev/disclaimer) and [Terms of Use](ToU.md) before using PHYSIS.

**P.H.Y.S.I.S. Production:** [https://physiscalcs.dev](https://physiscalcs.dev)

**Current release:** **v0.8.10** (22 Oct 2026) — Changelog sync from completed GitHub issues; pending-updates UI and related shipped work (see [`CHANGELOG.md`](CHANGELOG.md)).

## Primary workflow: growth & height prediction

The main workflow (`/growth`) guides TW3-RUS bone age scoring through adult height prediction and CDC growth chart visualization.


| Step                 | Feature                                                                                                                                                                                                                        |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **TW3 bone age**     | Hand-navigator scoring for all 13 RUS landmarks with per-stage drawings and criteria text (individual atlas PNGs + markdown descriptions), discrete stage slider, and SMS → bone age lookup (sex-specific Tables A1/A3, A5/A6) |
| **Parental stature** | Father/mother heights (cm, in, or ft+in) or direct MPH entry; distinguishes **MPH** (Tanner, TW3) from **MPS** (parental average, adjusted RWT & Khamis-Roche)                                                                 |
| **APH methods**      | Bone-age mode: **TW3**, **adjusted RWT**, **original RWT**. No-bone-age mode: **Khamis-Roche** only. Missing-input checklists on result cards before calculation.                                                              |
| **CDC growth chart** | Plots stature and weight vs chronological age and bone-age–shifted age; overlays MPH/MPS and selected predicted adult height                                                                                                   |
| **Show work / QC**   | Audit trail of inputs, coefficient lookup, landmark scoring, and discrepancy flags (`ShowWorkSection`)                                                                                                                         |
| **Clinical copy**    | Configurable charting summary with method references and TW3 atlas citations                                                                                                                                                   |




## Other calculators -- C.A.L.C.S.

**C**omprehensive **A**ction-**L**everaging **C**alculator **S**uite

### Adrenals/ Sex Steroids (`/calculators/adrenal`)

| Tool | Route |
| --- | --- |
| BSA (Haycock or Costeff weight-only) & steroid potency wean/converter | `/bsa-steroid` |
| 17OHP Intrepretation in Prematurity (Olgemöller 2003 and Pode-Shakked 2018) | `/cah-screening` |
| XY DSD Steroid Panel — post-hCG T/DHT, T/Δ4A, ASI; Esoterix T/DHT/Δ4A conversion | `/xy-dsd-steroid-panel` |

### Bone Health (`/calculators/bone-health`)

| Tool | Route |
| --- | --- |
| Renal electrolyte indices (TRP, CCR, spot UCa/UCr, TTKG) | `/renal-electrolytes` |
| Calcium dosing (enteral / parenteral) | `/calcium-dosing` |
| Figueras-Aloy MBDP risk-score | `/figueras-aloy-mbdp` |
| DXA BMD Interpretation | `/dxa-bmd-interpretation` |
| Bone Turnover labs | Coming soon |

Legacy routes `/trp` and `/ccr` redirect to `/renal-electrolytes`.

### Diabetes (`/calculators/diabetes`)

| Tool | Route |
| --- | --- |
| A1c ↔ GMI ↔ fructosamine ↔ eAG (Cohen et al. preferred; Young et al. alternate) | `/a1c-converter` |
| Insulin MDI → sliding scale (ISS) | `/insulin-mdi-iss` |
| Diluted ISS generation | `/insulin-diluted-iss` |
| TDD estimator and MDI calculator — bolus (½/whole U) or TDD / % basal / ISF / ICR | `/tdd-mdi` |
| Insulin Resistant Indices — HOMA-IR, QUICKI, SPISE, Matsuda (optional OGTT) | `/insulin-resistant-indices` |
| MODY Clinical Calculator — at diagnosis (age &lt; 20) or Exeter post-6-month PPV (≤35 y) | `/mody-clinical-calculator` |
| Glycemia Risk Index (GRI) Calculator — AGP % → TIR, GRI, hypo/hyper components, zones A–E | `/glycemia-risk-index` |

### Electrolytes/Fluids (`/calculators/electrolytes`)

| Tool | Route |
| --- | --- |
| Sodium balance & replacement (FWD, hypo/hypernatremia infusion guidance) | `/sodium-balance` |
| Hyperglycemia sodium correction | `/hyperglycemia-sodium-correction` |
| Calcium correction for albumin | `/calcium-albumin` |
| Maintenance IVF (Holliday–Segar) | `/maintenance-ivf` |
| Glucose infusion rate — IV and enteral | `/gir` |

### Gonad Auxology (`/calculators/gonad-auxology`)

| Tool | Route |
| --- | --- |
| Stretched penile length (newborn) — Halil et al. and Feldman/Aaronson nomograms | `/spl-newborn` |
| Stretched penile length (child) — Bulgarian, Schonfeld, and Feldman references | `/spl-child` |
| Clitoral length/width (neonate) — Alaei et al. nomogram | `/clitoral-dimension` |
| Uterine / ovarian SDS — Gilligan 2019 pelvic US mean±SD | `/uterine-ovary-sds` |

Legacy route `/calculators/normograms` redirects to `/calculators/gonad-auxology`.

### Outpatient Auxology (`/calculators/outpatient-auxology`)

| Tool | Route |
| --- | --- |
| Pediatric hypertensive BP percentiles (AAP 2017) | `/pediatric-bp` |
| Growth Velocity SDS — infant WHO–Tanner (≤5.9 y) or pediatric HV both ancestries (>5.9 y) | `/gv-sds` |
| Anthropometric ratio tools — SHOX/XO sit–stand and arm-span screening; sitting height SDS; ACH SH/LL SDS | `/anthropometric-ratio-tools` |
| Diagnosis-Specific Growth — Shyr GAMLSS condition height SDS/%ile (2–20 y; optional unaffected overlay) | `/diagnosis-specific-growth` |
| Physical Exam Staging Guide — Tanner/SMR, EGS, Prader, Quigley, Sinnecker, modified Ferriman–Gallwey | `/physical-exam-staging-guide` |

### Outpatient Endocrinology (`/calculators/outpatient-endocrinology`)

| Tool | Route |
| --- | --- |
| Long-Acting GH IGF Correction — Table 2 SDS timing factors (Ngenla / Skytrofa / Sogroya) | `/lagh-igf-correction` |
| IGF-1 / IGFBP-3 Z-score — multi-assay SDS + optional Tanner/SMR | `/igf1-zscore-roche` |
| GH dosing — Initiate & Titrate (daily/weekly; doses/week schedule; obese Costeff/Mosteller BSA; indication start ranges; calculated vs pen dose; selectable pen strengths with exact/rounded 28-day supply) | `/gh-dosing` |
| Levothyroxine dosing — age-based mcg/kg; optional BSA (100 mcg/m²) after 1 y | `/levothyroxine-dosing` |

### Lab References (`/calculators/lab-assays`)

| Tool | Route |
| --- | --- |
| EMR import + Esoterix RefRange tools — paste Epic or Cerner exports; age/sex/SMR/draw-time Esoterix USA ranges with flags | `/lab-interpretation` |
| Lab Search/ Conversion + Esoterix Reference Ranges | `/esoterix-labs` |

### PEARLS (`/calculators/pearls`) — planned; hub hidden in CALCS UI

| Tool | Route |
| --- | --- |
| Hormone and Receptor review | Coming soon |
| Genes and Genetics | Coming soon (`data/calc/genes-genetics.csv`) |

Collection meaning: Peds Endo Applied Review & Learning Strategies. Catalog entries remain in code for a future hub; not listed on `/calculators` until promoted. Pending work is tracked on [GitHub issues](https://github.com/doctor-dom/physis-calcs/issues).
