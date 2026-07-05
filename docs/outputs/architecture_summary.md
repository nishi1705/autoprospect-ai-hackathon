# AutoProspect AI Architecture Summary

## Architecture Pattern

AutoProspect AI uses a controlled, lightweight multi-agent orchestration pattern implemented inside a Google Colab notebook.

The system is designed for:

- Reproducibility
- Transparency
- Explainable scoring
- Controlled live public-source enrichment
- Safe LLM usage without hardcoded API keys

## End-to-End Flow

Product Handbook
→ Company Universe
→ Public Source Register
→ Live Web Research Agent
→ Evidence Enrichment Agent
→ Market Intelligence Agent
→ Product Knowledge Agent
→ Company Discovery Agent
→ Company Research Agent
→ Pain Signal Detection Agent
→ Solution Fit Agent
→ Opportunity Scoring Agent
→ Critic / Validation Agent
→ Business Recommendation Card Agent
→ Executive Market Research Report Agent
→ Source Intelligence Agent
→ GPT-4o mini Narrative Enhancement Agent
→ Executive Report + Outputs

## Main Components

1. **Configuration Layer**
   Defines target industry, target company count, output folder, live web settings, and LLM model configuration.

2. **Product Knowledge Layer**
   Converts the XYZ Analytics Consulting Product & Solutions Handbook into a structured product knowledge base covering Warranty Analytics, Supply Chain Risk Prediction, and Dealer & Field Service Intelligence.

3. **Company Universe Layer**
   Starts from a curated seed universe of Indian automotive OEMs, EV OEMs, Tier-1 suppliers, and component manufacturers.

4. **Public Source Register**
   Documents the public-source categories expected by the hackathon: company websites, LinkedIn, NSE/BSE, Moneycontrol, Screener, IBEF, SIAM, ACMA, Economic Times Auto, Autocar Professional, Google News, and the Product Handbook.

5. **Live Web Research Layer**
   Performs controlled live fetching from official company websites and Google News RSS. Requests are protected with timeout, user-agent, exception handling, and fallback logic.

6. **Evidence Enrichment Layer**
   Converts live website/news snippets into company-level evidence keywords, recent headline summaries, and evidence notes.

7. **Agent Workflow Layer**
   Runs specialized agents for market understanding, product validation, company research, pain detection, solution fit, scoring, validation, report generation, and LLM narrative enhancement.

8. **Decision Layer**
   Uses deterministic scoring for opportunity ranking so that Top 15 decisions are explainable and not dependent on the LLM.

9. **LLM Narrative Layer**
   Uses GPT-4o mini for executive pitch, business justification, personalized outreach angle, discovery questions, and source-validation guidance. The notebook captures request IDs and token usage as runtime proof.

10. **Output Layer**
   Generates CSV, JSON, HTML, Markdown, and PNG artifacts for review and GitHub packaging.

## Design Rationale

The architecture avoids a generic chatbot design. It behaves like an autonomous pre-sales intelligence workflow: source registration, live evidence gathering, profile enrichment, scoring, validation, recommendation, LLM-enhanced narrative, and final reporting.

## Reproducibility and Safety

- No API key is hardcoded.
- GPT-4o mini is used only when OPENAI_API_KEY is available in Colab Secrets.
- Live web research failures are captured as status rows and do not fail the notebook.
- Ranking remains deterministic and explainable.
- The final runtime verification checks live evidence, LLM request proof, output artifacts, and agent trace.

Generated on: 2026-07-05 03:49:08