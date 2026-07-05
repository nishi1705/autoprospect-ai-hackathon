# 06 Opportunity Scoring Engine

## Purpose

This document explains the deterministic opportunity scoring engine used by AutoProspect AI.

The scoring engine ranks companies transparently before GPT-4o mini is used for narrative enhancement.

---

## Why Deterministic Scoring

The final company ranking should be explainable and reproducible.

Therefore, GPT-4o mini does not decide the ranking.

The LLM improves communication quality, but the ranking is created by deterministic business rules.

---

## Scoring Dimensions

| Dimension | Weight |
|---|---:|
| Pain Intensity | 25 |
| Product Fit | 25 |
| Market Relevance | 15 |
| Growth / Investment Signal | 15 |
| Financial Capacity Proxy | 10 |
| Urgency / News Signal Proxy | 5 |
| Data Readiness Likelihood | 5 |
| Total | 100 |

---

## Priority Buckets

| Score Range | Priority |
|---:|---|
| 80–100 | Hot |
| 70–79 | Warm |
| 55–69 | Nurture |
| Below 55 | Low Priority |

---

## Confidence Logic

Confidence is based on score and evidence strength.

Higher scores and stronger evidence produce higher confidence.

The Critic / Validation Agent later reviews the recommendation and adds risk reasoning.

---

## Role of Live Evidence

Live evidence enrichment improves the quality of company context and validation.

The scoring still remains controlled and explainable.

---

## Output Files

The scoring engine exports:

```text
outputs/opportunity_pipeline_all_companies.csv
outputs/top15_target_companies.csv
outputs/critic_validation_output.csv
```

---

## Enterprise Benefit

The scoring approach makes the recommendation auditable.

A reviewer can understand why a company was ranked high instead of trusting an opaque LLM answer.
