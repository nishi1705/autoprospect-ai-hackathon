# 09 Live Web Research and GPT-4o mini Runtime Proof

## Purpose

This document explains the final enhancement added to AutoProspect AI: live web research, evidence enrichment, and GPT-4o mini runtime proof.

This step addresses the concern that the solution should not look fully hardcoded.

---

## Live Web Research Strategy

AutoProspect AI uses controlled live web research instead of uncontrolled scraping.

The notebook fetches:

- Official company website pages
- Google News RSS results for each company

It avoids aggressive scraping from sources that may block automation or require login, such as LinkedIn, NSE/BSE dynamic pages, Moneycontrol, and Screener.

These are still included in the public source register and company source mapping as validation sources.

---

## Live Research Implementation

The Live Web Research Agent:

1. Reads company names and official websites from the company universe.
2. Fetches official website HTML using safe request handling.
3. Fetches Google News RSS using company name search.
4. Extracts title, meta description, headings, and evidence snippets.
5. Captures fetch status and HTTP status.
6. Continues safely even if some websites fail.

---

## Evidence Enrichment

The Evidence Enrichment Agent converts raw fetched information into structured company-level evidence.

It captures:

- Evidence availability
- Number of successful sources
- Evidence keywords
- Website title
- News headlines
- Live evidence summary

---

## Expected Live Web Outputs

```text
outputs/live_web_research_evidence.csv
outputs/company_live_evidence_summary.csv
outputs/web_scraping_status_report.csv
```

In the validated run, the solution produced:

- 54 live evidence rows
- 27 companies with evidence coverage
- 27 Google News RSS successes
- 24 official website successes
- 3 official website failures handled safely

---

## GPT-4o mini Prompt Design

GPT-4o mini receives structured context from the deterministic agents.

The prompt instructs the model to:

- Act as a senior B2B pre-sales strategist
- Use only provided context
- Avoid inventing facts, financial numbers, customers, or news
- Return valid JSON only

The LLM generates:

- Executive pitch
- Enhanced business justification
- Personalized outreach angle
- Discovery questions
- Data sources to validate
- Caution note

---

## GPT-4o mini Runtime Proof

The production notebook records proof of fresh API execution.

It exports:

```text
outputs/llm_runtime_proof.csv
outputs/llm_runtime_proof.json
```

These files include:

- Runtime session ID
- Generated timestamp
- Company name
- LLM execution mode
- OpenAI request ID
- Model returned by API
- Prompt tokens
- Completion tokens
- Total tokens
- Status

---

## How to Confirm Fresh LLM Calls

After `Runtime → Restart session and run all`, check the GPT-4o mini runtime proof section.

Expected output:

```text
Completed GPT-4o mini calls: 15
Request IDs captured: 15
Total tokens captured: greater than 0
PASS: Fresh GPT-4o mini calls are confirmed for all Top 15 companies.
```

---

## Final Agent Trace

The final trace is exported as:

```text
outputs/agent_trace_step9_6.json
```

It should contain 14 agents, including:

- Live Web Research Agent
- Evidence Enrichment Agent
- LLM Narrative Enhancement Agent

---

## Final Verification

The final runtime verification should confirm:

```text
PASS: Notebook generated live web evidence, fresh GPT-4o mini enhanced output, runtime proof, 14-agent trace, and final artifacts.
```

This proves that the solution uses both live web evidence and real GPT-4o mini calls during execution.
