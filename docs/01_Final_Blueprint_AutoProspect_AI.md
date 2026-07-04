# 01 Final Blueprint: AutoProspect AI

## Product Name

**AutoProspect AI**  
**Agentic Sales Intelligence Platform for Automotive Analytics Consulting**

---

## 1. Problem Statement

XYZ Analytics Consulting is an automotive analytics consultancy that helps automotive OEMs, Tier-1 suppliers, and component manufacturers improve business performance through analytics-led solutions such as:

1. Warranty Analytics
2. Supply Chain Risk Prediction
3. Dealer & Field Service Intelligence

The sales team currently spends significant manual effort identifying potential customers, researching companies, understanding business challenges, and recommending suitable consulting offerings.

The hackathon challenge is to build an **AI-Powered Sales Intelligence Agent** that automates this process and recommends the **Top 10-15 target companies** with clear business justification.

---

## 2. Product Vision

> AutoProspect AI helps automotive analytics consulting firms discover, evaluate, prioritize, and engage high-potential B2B prospects using a multi-agent AI workflow.

The system should behave like a **virtual pre-sales intelligence team**, not like a simple chatbot.

---

## 3. What We Are Building

We are building a **Google Colab-based multi-agent sales intelligence solution**.

The solution will:

1. Understand the Indian automotive market.
2. Identify candidate companies across OEMs, Tier-1 suppliers, and component manufacturers.
3. Analyze company profile, business model, products, manufacturing footprint, growth signals, financial indicators, and recent developments.
4. Detect business pain signals.
5. Use XYZ Analytics Consulting's product handbook to understand consulting offerings.
6. Match each company's likely pain points with the right consulting solution.
7. Score and rank companies.
8. Recommend the **Top 10-15 target companies**.
9. Generate executive-ready business recommendations.
10. Export final reports and evidence.

---

## 4. What We Are Not Building

We are **not** building:

- A generic chatbot
- A simple RAG PDF Q&A bot
- A fancy external web application
- A separate React, Streamlit, or FastAPI product
- A system dependent on hidden local files
- A solution with hardcoded API keys

The final working solution must be delivered as a **single Google Colab notebook `.ipynb`**, runnable end-to-end.

---

## 5. Core Product Positioning

Most participants may create:

```text
Search -> Summarize -> Recommend
```

AutoProspect AI will create:

```text
Research -> Detect Pain -> Match Product -> Score Opportunity -> Validate -> Recommend -> Generate Sales Strategy
```

That is the difference between a chatbot and an agentic decision system.

---

## 6. Proposed Agentic Architecture

### Agent 1: Market Intelligence Agent

**Purpose:** Understands the Indian automotive market and identifies opportunity themes.

**Inputs:**

- Automotive market context
- Public source references
- Product handbook context

**Responsibilities:**

- Identify market trends
- Identify target segments
- Identify business pressures
- Connect market pressures with analytics opportunities

**Output Example:**

```json
{
  "market_segments": ["OEM", "Tier-1 Supplier", "Component Manufacturer"],
  "market_pressures": [
    "warranty cost pressure",
    "supply chain disruption",
    "dealer performance inconsistency",
    "EV transition complexity",
    "aftermarket growth"
  ],
  "opportunity_themes": [
    "quality analytics",
    "supplier risk prediction",
    "dealer performance intelligence"
  ]
}
```

---

### Agent 2: Company Discovery Agent

**Purpose:** Creates a candidate universe of Indian automotive companies.

**Inputs:**

- Candidate company list
- Market segments
- Automotive industry context

**Responsibilities:**

- Identify OEMs
- Identify Tier-1 suppliers
- Identify component manufacturers
- Classify each company

**Output Example:**

```json
{
  "company": "Tata Motors",
  "segment": "OEM",
  "category": "Passenger Vehicles, Commercial Vehicles, EV",
  "priority_for_research": "High"
}
```

---

### Agent 3: Company Research Agent

**Purpose:** Builds company-level intelligence.

**Inputs:**

- Company name
- Segment
- Public company information
- Pre-loaded company evidence table

**Responsibilities:**

For each company, collect:

- Company overview
- Products and services
- Manufacturing footprint
- Business growth signals
- Financial capacity indicators
- Recent news or strategic initiatives
- Likely business challenges

**Output Example:**

```json
{
  "company": "Mahindra & Mahindra",
  "overview": "...",
  "products": ["SUVs", "commercial vehicles", "tractors", "EVs"],
  "growth_signals": ["EV expansion", "SUV demand", "dealer network scale"],
  "business_challenges": ["supply chain complexity", "dealer performance visibility"]
}
```

---

### Agent 4: Pain Signal Detection Agent

**Purpose:** Detects business pain signals from company context.

**Inputs:**

- Company profile
- Growth signals
- Product portfolio
- Segment
- Market pressures

**Responsibilities:**

Identify whether the company likely faces:

- Warranty analytics need
- Supply chain risk need
- Dealer intelligence need
- Aftermarket opportunity
- EV-related analytics complexity
- Quality and recall risk
- Production and supplier dependency

**Output Example:**

```json
{
  "company": "Tata Motors",
  "pain_signals": {
    "warranty_complexity": "High",
    "dealer_network_complexity": "High",
    "supply_chain_complexity": "Medium",
    "ev_transition_complexity": "High"
  }
}
```

---

### Agent 5: Product Knowledge Agent

**Purpose:** Understands XYZ Analytics Consulting's offerings from the product handbook.

**Inputs:**

- XYZ Analytics Consulting Product & Solutions Handbook

**Responsibilities:**

Convert handbook content into structured product intelligence.

XYZ's main offerings are:

1. Warranty Analytics
2. Supply Chain Risk Prediction
3. Dealer & Field Service Intelligence

**Output Example:**

```json
{
  "solution": "Warranty Analytics",
  "pain_points": [
    "warranty cost",
    "claim spikes",
    "defect detection",
    "recall risk",
    "quality leakage"
  ],
  "kpis": [
    "Defects per 1000 vehicles",
    "MTBF",
    "Warranty spend per unit",
    "Claim cycle time",
    "Recall incidence rate"
  ],
  "business_value": [
    "early defect detection",
    "reduced warranty cost",
    "improved quality response"
  ]
}
```

---

### Agent 6: Solution Fit Agent

**Purpose:** Maps company pain signals to the most relevant XYZ consulting offering.

**Inputs:**

- Pain signals
- Product knowledge
- Company profile

**Responsibilities:**

Recommend:

- Primary consulting solution
- Secondary consulting solution
- Why the solution fits
- Expected business value

**Output Example:**

```json
{
  "company": "Tata Motors",
  "primary_solution": "Warranty Analytics",
  "secondary_solution": "Dealer & Field Service Intelligence",
  "fit_reason": "Large vehicle portfolio, EV growth, warranty complexity, and dealer network scale create strong analytics opportunity."
}
```

---

### Agent 7: Opportunity Scoring Agent

**Purpose:** Ranks companies using a transparent scoring model.

**Inputs:**

- Company research output
- Pain signal output
- Solution fit output
- Market relevance

**Scoring Dimensions:**

| Dimension | Weight |
|---|---:|
| Pain Intensity | 25 |
| Product Fit | 25 |
| Market Relevance | 15 |
| Growth / Investment Signal | 15 |
| Financial Capacity | 10 |
| Urgency / News Signal | 5 |
| Data Readiness Likelihood | 5 |
| **Total** | **100** |

**Priority Logic:**

| Score Range | Priority |
|---:|---|
| 85-100 | Hot |
| 70-84 | Warm |
| 55-69 | Nurture |
| Below 55 | Low Priority |

**Output Example:**

```json
{
  "company": "Mahindra & Mahindra",
  "opportunity_score": 90,
  "priority": "Hot",
  "confidence": "High"
}
```

---

### Agent 8: Critic / Validation Agent

**Purpose:** Challenges the recommendation before final output.

Most solutions will only recommend. AutoProspect AI will also ask:

> Why may this recommendation be weak?

**Responsibilities:**

- Check whether the selected solution is too generic
- Check whether the score is justified
- Identify potential objections
- Add negative reasoning
- Improve trustworthiness

**Output Example:**

```json
{
  "company": "Maruti Suzuki",
  "validation_status": "Accepted",
  "why_not": "May already have mature internal analytics capability; pitch should focus on advanced predictive warranty and dealer intelligence rather than basic dashboards."
}
```

---

### Agent 9: Executive Report Agent

**Purpose:** Generates final business-ready output.

**Responsibilities:**

- Market research report
- Top 10-15 companies
- Company-wise recommendation cards
- Business justification
- Sales conversation starters
- Final executive summary
- Exportable reports

**Output:**

```text
Final Sales Intelligence Report
Top 15 Target Companies
Opportunity Pipeline
Company Recommendation Cards
Executive Summary
Architecture Diagram
Agent Trace
```

---

## 7. High-Level Architecture Diagram

```text
                         ┌──────────────────────────┐
                         │ User Mission / Config    │
                         │ Find Top 15 Prospects    │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │ Market Intelligence      │
                         │ Agent                    │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │ Company Discovery        │
                         │ Agent                    │
                         └────────────┬─────────────┘
                                      │
                                      ▼
         ┌───────────────────┐   ┌──────────────────────────┐
         │ Public Sources    │──▶│ Company Research         │
         │ Websites / News   │   │ Agent                    │
         └───────────────────┘   └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │ Pain Signal Detection    │
                         │ Agent                    │
                         └────────────┬─────────────┘
                                      │
                                      ▼
         ┌───────────────────┐   ┌──────────────────────────┐
         │ XYZ Product       │──▶│ Product Knowledge        │
         │ Handbook          │   │ Agent                    │
         └───────────────────┘   └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │ Solution Fit Agent       │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │ Opportunity Scoring      │
                         │ Agent                    │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │ Critic / Validation      │
                         │ Agent                    │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │ Executive Report Agent   │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │ Final Deliverables       │
                         │ Top 10-15 Companies      │
                         │ Market Report            │
                         │ Business Recommendations │
                         │ Agent Trace              │
                         └──────────────────────────┘
```

---

## 8. Data Model

### Table 1: Company Universe

| Field | Meaning |
|---|---|
| company_name | Name of company |
| segment | OEM / Tier-1 / Component Manufacturer |
| category | Passenger vehicle, commercial vehicle, EV, component, battery, etc. |
| website | Company website |
| business_notes | Short business profile |
| products | Key products |
| footprint | Manufacturing / market presence |
| growth_signals | EV, expansion, exports, new plants, etc. |
| evidence_notes | Source-based notes or preloaded evidence |

### Table 2: Product Knowledge

| Field | Meaning |
|---|---|
| solution_name | Warranty Analytics / Supply Chain Risk / Dealer Intelligence |
| pain_points | Business problems solved |
| capabilities | Main analytics capabilities |
| kpis | KPIs tracked |
| business_value | Value delivered |
| target_segments | Best-fit customer types |
| sample_pitch | Sales angle |

### Table 3: Scoring Output

| Field | Meaning |
|---|---|
| company_name | Company |
| pain_intensity_score | 0-25 |
| product_fit_score | 0-25 |
| market_relevance_score | 0-15 |
| growth_signal_score | 0-15 |
| financial_capacity_score | 0-10 |
| urgency_score | 0-5 |
| data_readiness_score | 0-5 |
| total_score | 0-100 |
| priority | Hot / Warm / Nurture / Low |
| recommended_solution | Best-fit XYZ solution |
| confidence | High / Medium / Low |

### Table 4: Final Recommendation

| Field | Meaning |
|---|---|
| rank | Final rank |
| company_name | Company |
| segment | OEM / Tier-1 / Component Manufacturer |
| recommended_solution | Primary solution |
| secondary_solution | Optional second solution |
| why_selected | Business justification |
| expected_business_value | Expected value |
| sales_conversation_starter | Suggested sales opener |
| why_not_risk | Objection / limitation |
| priority | Hot / Warm / Nurture |
| confidence | High / Medium / Low |

---

## 9. Colab Notebook Wireframe

The notebook should become the product interface.

### Section 1: Title

```text
AutoProspect AI
Agentic Sales Intelligence Platform for XYZ Analytics Consulting
```

### Section 2: Problem Statement

Explain the business challenge in 5-7 lines.

### Section 3: Setup

Install and import required libraries.

Possible libraries:

```python
pandas
numpy
json
textwrap
datetime
IPython.display
openai
```

Optional libraries:

```python
plotly
networkx
```

### Section 4: Configuration

```python
RUN_MODE = "DEMO"
USE_LLM = False
MODEL_NAME = "gpt-4o-mini"
TARGET_COMPANIES = 15
```

Default should be `DEMO` and `USE_LLM = False`, so reviewers can run it without an API key.

### Section 5: Product Knowledge Load

Load structured product knowledge from the handbook.

### Section 6: Company Universe

Load 20-25 candidate companies.

### Section 7: Agent Definitions

Define each agent as a Python function or class.

Example:

```python
def market_intelligence_agent(state):
    return updated_state
```

### Section 8: Agent Workflow Execution

Run agents one by one and show trace.

```text
Market Intelligence Agent completed
Company Discovery Agent completed
Company Research Agent completed
Pain Signal Agent completed
Product Knowledge Agent completed
Solution Fit Agent completed
Opportunity Scoring Agent completed
Critic Agent completed
Executive Report Agent completed
```

### Section 9: Opportunity Pipeline

Show ranked table.

### Section 10: Company Recommendation Cards

Show top company cards using Markdown or HTML.

### Section 11: Market Research Report

Generate summarized market report.

### Section 12: Architecture Diagram

Show Mermaid or text diagram.

### Section 13: Export Outputs

Export:

```text
final_recommendations.csv
executive_report.md
agent_trace.json
sales_intelligence_report.html
```

### Section 14: Assumptions and Limitations

Mention clearly:

- Public-source research may vary over time.
- Demo mode uses curated company intelligence.
- Live mode can use LLM/API-based enrichment.
- Financial details are indicative and should be validated before real sales action.
- API keys are not included in notebook.

---

## 10. LLM Strategy

### Model Choice

Use:

```text
gpt-4o-mini
```

### Why it is sufficient

GPT-4o mini should be sufficient because the architecture does not depend fully on the model for decision-making.

We will use:

```text
Deterministic scoring + structured evidence + GPT-4o mini narrative generation
```

GPT-4o mini will help with:

- Professional executive summaries
- Business justification
- Solution fit narrative
- Sales conversation starter
- Final recommendation language

The score itself will be deterministic and explainable.

---

## 11. UI Strategy

No separate UI is required.

The final solution must be a Google Colab notebook. Therefore, the notebook itself will be designed as a lightweight product UI using:

- Markdown headers
- Styled tables
- HTML cards
- Downloadable reports
- Architecture diagram
- Visible outputs

This is safer than building Streamlit or Gradio because the final deliverable must run end-to-end in Colab.

---

## 12. GitHub Repository Structure

Later, we will create this structure:

```text
autoprospect-ai/
│
├── AutoProspect_AI_Hackathon.ipynb
├── README.md
├── outputs/
│   ├── final_recommendations.csv
│   ├── executive_report.md
│   ├── agent_trace.json
│   └── sales_intelligence_report.html
│
├── docs/
│   ├── architecture_diagram.png
│   └── solution_blueprint.md
│
└── LICENSE
```

For the hackathon, the minimum required files are:

- Notebook
- README
- Architecture diagram
- Visible outputs or generated files

---

## 13. Final Deliverables Mapping

| Hackathon Expectation | AutoProspect AI Deliverable |
|---|---|
| AI Agent Demonstration | Colab notebook with multi-agent workflow |
| Market Research Report | Notebook section + exported executive report |
| Top 10-15 Target Companies | Ranked opportunity pipeline |
| Business Recommendations | Company 360 recommendation cards |
| Architecture Diagram | Mermaid/text diagram + image |
| Source Code | Single Colab notebook in GitHub |
| README | Setup, approach, tools, assumptions, limitations |
| Runnable Notebook | Demo mode and optional LLM mode |

---

## 14. Success Criteria

AutoProspect AI should stand out because it demonstrates:

1. Clear understanding of business problem
2. Strong product thinking
3. Agentic workflow, not chatbot behavior
4. Use of product handbook
5. Transparent scoring logic
6. Explainable recommendations
7. Negative reasoning through Critic Agent
8. Reproducible Colab notebook
9. Clean documentation
10. Professional consulting-style output

---

## 15. Step 1 Completion Status

| Item | Status |
|---|---|
| Product name finalized | Completed |
| Problem statement finalized | Completed |
| Vision finalized | Completed |
| Agent architecture finalized | Completed |
| Data model drafted | Completed |
| Notebook wireframe drafted | Completed |
| LLM strategy decided | Completed |
| UI strategy decided | Completed |
| GitHub structure drafted | Completed |
| Deliverables mapping completed | Completed |

---

## 16. Current Project Status Tracker

| Area | Status |
|---|---|
| Problem statement understood | Completed |
| Guidelines reviewed | Completed |
| Product handbook reviewed | Completed |
| Solution strategy | Completed |
| Google Colab development | Not started |
| GitHub setup | Not started |
| README | Not started |
| Architecture diagram | Draft completed |
| Final notebook | Not started |
| Final submission | Not started |

---

## 17. Source Documents Reviewed

1. Hackathon Problem Statement.pdf
2. XYZ Analytics Consulting - Product & Solutions Handbook.pdf
3. Hackathon Guidelines.pdf

---

**Prepared for:** INTTRVU AI Innovation Hackathon 2026  
**Solution:** AutoProspect AI  
**Prepared by:** Nishikant Phapale  
**Date:** 04 July 2026
