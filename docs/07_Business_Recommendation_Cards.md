# 07 Business Recommendation Cards

## Purpose

This document explains how AutoProspect AI converts scoring results into business-ready recommendation cards.

Recommendation cards are designed for sales and consulting stakeholders.

---

## Card Content

Each recommendation card includes:

- Rank
- Company name
- Segment
- Opportunity score
- Priority
- Confidence
- Primary solution
- Secondary solution
- Why selected
- Business challenges
- Recommended solution rationale
- Expected business value
- Relevant KPIs
- Suggested stakeholders
- Sales conversation starter
- Recommended next action
- Critic / why-not risk

---

## Role in the Workflow

```text
Opportunity Scoring
        ↓
Critic Validation
        ↓
Business Recommendation Card Agent
        ↓
GPT-4o mini Narrative Enhancement
```

---

## Why Cards Are Important

The hackathon asks not only for a technical output, but for business recommendations.

Recommendation cards make the output easy for a sales team to use.

---

## Output Files

The notebook exports:

```text
outputs/top15_recommendation_cards.csv
outputs/top15_recommendation_cards.json
outputs/top15_recommendation_cards.html
```

---

## LLM Enhancement

After deterministic cards are generated, GPT-4o mini enriches the business narrative.

The LLM-enhanced output is exported separately:

```text
outputs/top15_llm_enhanced_recommendations.csv
outputs/top15_llm_enhanced_recommendations.json
```

This keeps the original deterministic recommendation separate from the LLM narrative.
