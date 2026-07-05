# AutoProspect AI

## Agentic Sales Intelligence Platform for Automotive Analytics Consulting

AutoProspect AI is a Google Colab-based Agentic AI solution developed for the INTTRVU AI Innovation Hackathon 2026.

The solution helps XYZ Analytics Consulting identify, analyze, prioritize, and recommend high-potential Indian automotive companies for its analytics consulting offerings.

---

## 1. Problem Statement

XYZ Analytics Consulting wants to accelerate B2B sales prospecting in the Indian automotive sector.

The objective is to build an AI-powered Sales Intelligence Agent that can:

- Research the Indian automotive industry
- Identify Automotive OEMs, Tier-1 suppliers, and component manufacturers
- Analyze public company information
- Detect business challenges and buying signals
- Map company challenges to XYZ Analytics Consulting offerings
- Recommend the Top 10–15 target companies
- Generate business-ready sales recommendations

---

## 2. Final Solution Overview

AutoProspect AI works as a virtual pre-sales research team.

It uses:

- Structured product knowledge from the provided XYZ Product & Solutions Handbook
- Candidate company universe for Indian automotive companies
- Public source register aligned with hackathon guidelines
- Live web research from official company websites and Google News RSS
- Evidence enrichment for company-level signals
- Deterministic opportunity scoring for explainable ranking
- Critic / validation logic for recommendation quality
- GPT-4o mini for LLM-powered narrative enhancement
- Final reports and artifacts in CSV, JSON, HTML, Markdown, and PNG formats

---

## 3. Core Offerings Used

The solution uses the provided XYZ Product & Solutions Handbook and structures three consulting offerings:

1. Warranty Analytics
2. Supply Chain Risk Prediction
3. Dealer & Field Service Intelligence

---

## 4. Agentic AI Workflow

AutoProspect AI is not a single-prompt chatbot. It uses a controlled multi-agent workflow.

Final agent sequence:

1. Product Knowledge Agent
2. Company Discovery Agent
3. Public Source Register / Source Intelligence Agent
4. Live Web Research Agent
5. Evidence Enrichment Agent
6. Market Intelligence Agent
7. Company Research Agent
8. Pain Signal Detection Agent
9. Solution Fit Agent
10. Opportunity Scoring Agent
11. Critic / Validation Agent
12. Business Recommendation Card Agent
13. Executive Market Research Report Agent
14. LLM Narrative Enhancement Agent

Each agent performs a defined task and produces structured output. The workflow also generates an agent trace for explainability and auditability.

---

## 5. Data Sources

The hackathon suggested the following source categories:

- Official company websites
- LinkedIn company pages
- NSE India
- BSE India
- Moneycontrol
- Screener
- IBEF
- SIAM
- ACMA
- Economic Times Auto
- Autocar Professional
- Google News
- XYZ Product & Solutions Handbook

The solution uses these in two ways:

### 5.1 Live Web Research

The notebook performs controlled live research from:

- Official company websites
- Google News RSS

It extracts:

- Page title
- Meta description
- Headings
- Evidence snippets
- News headlines
- Business signal keywords

### 5.2 Source Mapping

Some public sources such as LinkedIn, NSE/BSE, Moneycontrol, and Screener may have login, bot protection, or dynamic rendering restrictions. These are included as validation and enrichment sources through the public source register and company-wise source mapping.

This design keeps the notebook reliable in Google Colab while still demonstrating real web research capability.

---

## 6. LLM Usage

The solution uses OpenAI GPT-4o mini for business narrative enhancement.

GPT-4o mini is used for:

- Executive sales pitch generation
- Business justification refinement
- Personalized outreach angle
- Discovery questions
- Source validation guidance

The LLM does not decide the ranking. Final ranking is generated using deterministic scoring for transparency and explainability.

API keys are not hardcoded. The notebook reads the OpenAI API key through Google Colab Secrets.

---

## 7. LLM Runtime Proof

The notebook generates LLM runtime proof files:

- `outputs/llm_runtime_proof.csv`
- `outputs/llm_runtime_proof.json`

These files capture:

- Runtime session ID
- Timestamp
- Company name
- Model used
- Request ID
- Prompt tokens
- Completion tokens
- Total tokens
- Execution status

This proves that GPT-4o mini was called during the latest notebook run.

---

## 8. Technology Stack

- Google Colab
- Python
- Pandas
- NumPy
- Requests
- BeautifulSoup
- Matplotlib
- OpenAI GPT-4o mini
- Custom lightweight multi-agent orchestration
- CSV / JSON / HTML / Markdown / PNG outputs

---

## 9. How to Run

1. Open `notebook/AutoProspect_AI_Hackathon.ipynb` in Google Colab.
2. Add your OpenAI API key in Colab Secrets:
   - Secret name: `OPENAI_API_KEY`
   - Enable notebook access
3. Run:
   - `Runtime → Restart session and run all`
4. The notebook will generate all outputs inside the `outputs/` folder.
5. Review the final runtime verification section at the end of the notebook.

Expected final verification:

```text
PASS: Notebook generated live web evidence, fresh GPT-4o mini enhanced output, runtime proof, 14-agent trace, and final artifacts.
```

---

## 10. Main Outputs

Important output files:

| File | Purpose |
|---|---|
| `outputs/top15_target_companies.csv` | Final ranked Top 15 companies |
| `outputs/top15_recommendation_cards.html` | Business-ready recommendation cards |
| `outputs/top15_llm_enhanced_recommendations.csv` | GPT-4o mini enhanced sales narratives |
| `outputs/executive_market_research_report.md` | Final market research report |
| `outputs/executive_market_research_report.html` | HTML version of executive report |
| `outputs/architecture_diagram.png` | Solution architecture diagram |
| `outputs/public_source_register.csv` | Public data-source register |
| `outputs/company_source_mapping_top15.csv` | Company-wise source mapping |
| `outputs/live_web_research_evidence.csv` | Live web research evidence |
| `outputs/company_live_evidence_summary.csv` | Company-wise live evidence summary |
| `outputs/web_scraping_status_report.csv` | Web scraping success/failure summary |
| `outputs/llm_runtime_proof.csv` | GPT-4o mini request and token proof |
| `outputs/agent_trace_step9_6.json` | 14-agent workflow trace |
| `outputs/final_quality_summary.json` | Final QA summary |
| `outputs/final_deliverable_checklist.csv` | Hackathon deliverable checklist |

---

## 11. Scoring Model

The opportunity scoring model uses deterministic scoring.

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

Priority buckets:

| Score Range | Priority |
|---:|---|
| 80–100 | Hot |
| 70–79 | Warm |
| 55–69 | Nurture |
| Below 55 | Low Priority |

---

## 12. Final Results

The notebook analyzes 27 Indian automotive companies and recommends the Top 15 target companies for XYZ Analytics Consulting.

The solution generates:

- Ranked target company list
- Business recommendation cards
- Live evidence summaries
- Critic-agent risk reasoning
- Suggested stakeholders
- Sales conversation starters
- GPT-4o mini enhanced executive narratives
- Executive market research report
- Architecture diagram
- Final QA and runtime proof

---

## 13. Repository Structure

```text
AutoProspect_AI_Hackathon/
│
├── README.md
│
├── assets/
│   └── Optional images and supporting assets
│
├── notebook/
│   └── AutoProspect_AI_Hackathon.ipynb
│
├── docs/
│   ├── 01_Final_Blueprint_AutoProspect_AI.md
│   ├── 02_Development_Environment_Setup_Run_Guide.md
│   ├── 03_Product_Knowledge_Model.md
│   ├── 04_Company_Universe_Model.md
│   ├── 05_Agent_Workflow_Foundation.md
│   ├── 06_Opportunity_Scoring_Engine.md
│   ├── 07_Business_Recommendation_Cards.md
│   ├── 08_Executive_Report_Architecture.md
│   ├── 09_Live_Web_Research_and_LLM_Runtime_Proof.md
│   └── 10_Final_QA_and_GitHub_Packaging.md
│
├── outputs/
│   └── Generated solution artifacts
│
└── solution_documentation/
    └── AutoProspect_AI_Complete_Solution_Documentation.docx
```

---

## 14. Assumptions and Limitations

- The notebook is designed as a hackathon-ready MVP and runs end-to-end in Google Colab.
- The company universe is curated for reproducibility and then enriched with live web evidence.
- Live web research may have partial failures due to website blocking, timeout, SSL, or dynamic rendering.
- LinkedIn and certain financial portals are treated as validation sources instead of aggressively scraped.
- GPT-4o mini is used for narrative enhancement, not final ranking.
- Recommendations should be reviewed by a human analyst before real sales outreach.
- No API keys or secrets are stored in the repository.

---

## 15. Productionization Potential

The solution can be productionized as a cloud-native sales intelligence platform using:

- Frontend dashboard
- Backend API services
- Agent orchestration service
- Scheduled web research pipeline
- Company intelligence database
- Vector search / knowledge retrieval
- LLM gateway
- AIOps and LLMOps monitoring
- Human approval workflow
- CRM integration

The current Colab notebook proves the business workflow and technical feasibility.

---

## 16. Status

Final solution package ready for INTTRVU AI Innovation Hackathon 2026 submission.
