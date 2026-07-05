# 02 Development Environment, Setup, and Run Guide

## Purpose

This document explains how to run AutoProspect AI in Google Colab and how to verify that live web research and GPT-4o mini are working correctly.

This file fills the missing `02_*.md` documentation slot and should be included in the final `docs/` folder.

---

## Mandatory Environment

The hackathon guideline requires the final working solution to be delivered as a single Google Colab notebook.

AutoProspect AI is implemented as:

```text
AutoProspect_AI_Hackathon_Production_Ready.ipynb
```

The notebook is designed to run end-to-end in Google Colab.

---

## Required Secret

GPT-4o mini is called through the OpenAI API.

The API key must not be hardcoded.

In Google Colab:

1. Open the key icon from the left sidebar.
2. Create a new secret.
3. Secret name:

```text
OPENAI_API_KEY
```

4. Paste the OpenAI API key as value.
5. Enable notebook access.

---

## Recommended Run Method

Use:

```text
Runtime → Restart session and run all
```

This verifies that the notebook runs cleanly from a fresh runtime.

---

## Expected Runtime Flow

The notebook should execute the following stages:

1. Configuration and setup
2. Product knowledge model
3. Company universe
4. Public source register
5. Live web research
6. Evidence enrichment
7. Agentic workflow
8. Opportunity scoring
9. Recommendation cards
10. Executive report and architecture
11. GPT-4o mini narrative enhancement
12. Runtime proof
13. Final QA
14. Final output export

---

## How to Confirm Live Web Research Ran

Check the final verification output for:

```text
Live evidence rows: greater than 0
Unique companies in live evidence: 27
Evidence summary rows: 27
```

Expected files:

```text
outputs/live_web_research_evidence.csv
outputs/company_live_evidence_summary.csv
outputs/web_scraping_status_report.csv
```

---

## How to Confirm GPT-4o mini Ran

The production notebook includes a dedicated GPT-4o mini runtime proof step.

Check the section:

```text
9.5 GPT-4o mini Runtime Proof
```

Expected result:

```text
Completed GPT-4o mini calls: 15
Request IDs captured: 15
Total tokens captured: greater than 0
PASS: Fresh GPT-4o mini calls are confirmed for all Top 15 companies.
```

Expected proof files:

```text
outputs/llm_runtime_proof.csv
outputs/llm_runtime_proof.json
```

These files capture:

- Runtime session ID
- Timestamp
- Company name
- Request ID
- Model returned by API
- Prompt tokens
- Completion tokens
- Total tokens
- Status

---

## Output Folder Significance

The `outputs/` folder is the evidence folder for the hackathon.

The notebook is the engine. The `outputs/` folder contains the generated deliverables.

It proves that the notebook ran and produced reviewable business artifacts.

---

## Important Note About Colab Storage

Colab local storage is temporary.

After the final run:

1. Save the notebook.
2. Download the notebook locally.
3. Download or zip the `outputs/` folder.
4. Upload selected outputs to GitHub.

---

## Final Expected QA Result

The final runtime verification should show:

```text
PASS: Notebook generated live web evidence, fresh GPT-4o mini enhanced output, runtime proof, 14-agent trace, and final artifacts.
```

If the OpenAI dashboard is delayed, rely on `llm_runtime_proof.csv` as the primary in-notebook proof.
