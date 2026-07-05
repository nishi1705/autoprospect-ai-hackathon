# 05 Agent Workflow Foundation

## Purpose

This document explains the custom lightweight multi-agent orchestration implemented in AutoProspect AI.

The workflow is designed to be reliable in Google Colab while still demonstrating Agentic AI behavior.

---

## Why Custom Agent Orchestration

The hackathon allows Agno, CrewAI, or any other open-source agent orchestration framework.

AutoProspect AI uses custom lightweight Python orchestration because:

- It is stable in Google Colab
- It avoids dependency failures
- It is easy for reviewers to run
- It provides transparent agent trace logging
- It supports deterministic and LLM-enhanced stages

---

## Shared Agent State

All agents communicate through a shared `agent_state` object.

The shared state stores:

- Configuration
- Product knowledge
- Company universe
- Source register
- Live web evidence
- Evidence summaries
- Market intelligence
- Company research
- Pain signals
- Solution fit output
- Opportunity scoring
- Recommendation cards
- LLM enhanced recommendations
- Agent trace

---

## Agent Trace

Every agent writes a trace entry with:

- Timestamp
- Agent name
- Action performed
- Input summary
- Output summary
- Status

The final trace is exported as:

```text
outputs/agent_trace_step9_6.json
```

---

## Final Agent Sequence

```text
Source Intelligence Agent
        ↓
Live Web Research Agent
        ↓
Evidence Enrichment Agent
        ↓
Market Intelligence Agent
        ↓
Product Knowledge Agent
        ↓
Company Discovery Agent
        ↓
Company Research Agent
        ↓
Pain Signal Detection Agent
        ↓
Solution Fit Agent
        ↓
Opportunity Scoring Agent
        ↓
Critic / Validation Agent
        ↓
Business Recommendation Card Agent
        ↓
Executive Market Research Report Agent
        ↓
LLM Narrative Enhancement Agent
```

---

## Why This Is Agentic

The solution is agentic because it decomposes the business problem into specialized decision stages.

Each stage has a responsibility and produces structured output consumed by the next stage.

This is different from a single LLM prompt or static report.

---

## Production Design Principle

The workflow separates:

- Data collection
- Evidence enrichment
- Deterministic decisioning
- Critic validation
- LLM narrative generation
- Final reporting

This separation improves explainability and reduces hallucination risk.
