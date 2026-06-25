# GMP Documentation Intelligence

**Nathan Qin / NathanTwin Intelligence** · Personal Research Brief · June 2026

A colleague at Sanofi described the daily reality of pharmaceutical GMP (Good Manufacturing Practice) management: drowning in documents, spending 40–60% of their time on manual correctness checking, and failing with every AI tool they tried.

This brief maps the problem precisely, diagnoses why AI fails in GMP contexts, and frames a build strategy using Harvey (legal) and Ketryx (regulatory software) as proven architectures.

## What's Inside

- **Live FDA Data** — Real-time GMP enforcement actions from openFDA drug enforcement API
- **AI Player Landscape** — Evidence-based capability matrix of all major GMP AI tools
- **Failure Mode Analysis** — Scientific diagnosis of why existing AI tools fail GMP managers
- **Sanofi Case Study** — QualiPSO program and the documentation pipeline
- **Architecture Design** — Four-layer system that satisfies both regulatory validity and correctness constraints
- **Regulatory Timeline** — EMA Annex 22 window (2026–2028)
- **Brain Nodes** — Knowledge points ready for Obsidian / Donna brain wiring

## Live APIs Wired

| Jurisdiction | Institution | API Status |
|---|---|---|
| 🇺🇸 US | FDA openFDA Drug Enforcement | ✦ Live REST API |
| 🇪🇺 EU | EMA / Europe PMC | ✦ Live REST API |
| 🇯🇵 Japan | PMDA | ◎ PubMed proxy |
| 🇨🇳 China | NMPA | ◈ Portal reference |

## Bruce Integration (NathanTwin Research Agent)

Added GMP routing to Bruce (`bruce.py`) and five new API clients to `clinical_apis.py`:
- `openfda_drug_enforcement()` — FDA drug recalls / GMP enforcement
- `openfda_drug_event()` — FAERS adverse events
- `ema_medicines()` — EMA regulatory intelligence via Europe PMC
- `pmda_notices()` — Japan PMDA via PubMed affil filter
- `nmpa_china()` — China NMPA via PubMed affil filter

Ask Bruce: *"What GMP manufacturing recalls has FDA issued in the last 6 months?"* → live openFDA data.

## View

Open `index.html` in any browser. Live FDA data loads from openFDA on page load.

---

*Nathan Qin · NathanTwin Intelligence · Personal project, not affiliated with any employer.*
