# 04 Company Universe Model

## Purpose

This document explains how the initial Indian automotive company universe is modeled in AutoProspect AI.

The company universe is the controlled seed list used for research, scoring, live web enrichment, and recommendation generation.

---

## Company Coverage

The notebook analyzes 27 Indian automotive companies across:

- OEMs
- Tier-1 suppliers
- Component manufacturers
- EV OEMs
- Automotive ecosystem players

---

## Why a Seed Universe Is Used

A real enterprise sales intelligence workflow usually starts with a candidate universe and then enriches it with external evidence.

AutoProspect AI follows this pattern:

```text
Seed Company Universe
        ↓
Live Web Research
        ↓
Evidence Enrichment
        ↓
Scoring and Recommendation
```

This avoids relying on fragile live discovery alone while still proving that live research is used.

---

## Company Attributes

Each company record includes:

- Company name
- Segment
- Category
- Website
- Business notes
- Products and services
- Manufacturing footprint
- Growth signals
- Likely data assets
- Initial relevance tags
- Evidence notes
- Source categories

---

## Role in Live Web Research

The `website` field is used by the Live Web Research Agent to fetch official company pages.

The company name is also used to generate Google News RSS search queries.

---

## Output Files

The notebook exports:

```text
outputs/company_universe.csv
outputs/company_universe.json
```

---

## Final Validation

The company universe is validated for:

- Minimum candidate count
- Missing fields
- Duplicate company names
- Segment coverage

This ensures the downstream workflow starts from a consistent company base.
