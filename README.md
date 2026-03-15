# ⚡ FlowForge AI

> **Autonomous AI-Driven SDLC Orchestration** — From PRD to Executive Dashboard, fully orchestrated by Claude-powered agents.

![FlowForge AI Banner](https://img.shields.io/badge/FlowForge-AI-1A56DB?style=for-the-badge&logo=anthropic&logoColor=white)
![Powered by Claude](https://img.shields.io/badge/Powered%20by-Anthropic%20Claude%20API-06B6D4?style=for-the-badge)
![MIT Coursework](https://img.shields.io/badge/Applied%20AI-MIT%20Coursework-F59E0B?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Conceptual%20Demo-10B981?style=for-the-badge)

---

## 🧠 What Is FlowForge AI?

FlowForge AI is a **conceptual agentic platform** that demonstrates how an AI-native engineering team could automate the entire Software Development Lifecycle (SDLC) — from parsing a Product Requirements Document all the way to delivering a voice-narrated executive briefing — using specialized Claude-powered agents at every stage.

This project was designed to showcase:
- **Systems-level AI architecture** applied to a real-world engineering problem
- **Agentic orchestration patterns** using the Anthropic Claude API
- **End-to-end SDLC automation** across 5 distinct workflow layers

---

## 🗺️ System Architecture

```
┌──────────────────────────────────────────────────────────────────────────┐
│                          FlowForge AI — 5 Layers                         │
├──────────────┬──────────────┬──────────────┬─────────────┬───────────────┤
│  LAYER 01    │  LAYER 02    │  LAYER 03    │  LAYER 04   │  LAYER 05     │
│  Ingestion   │  Planning    │  Execution   │  Review     │  Reporting    │
├──────────────┼──────────────┼──────────────┼─────────────┼───────────────┤
│ PRD Upload   │ FRD → Sprint │ Ticket →     │ PR Diff →   │ Metrics →     │
│     ↓        │   Backlog    │   Code       │   Review    │  Dashboard    │
│ FRD + ERD    │     ↓        │     ↓        │     ↓       │     ↓         │
│ Generated    │ Jira Tickets │ PR + Defects │ Gate Check  │ Voice Brief   │
└──────────────┴──────────────┴──────────────┴─────────────┴───────────────┘
                     All layers powered by Anthropic Claude API
```

---

## 🤖 Agent Roster (14 Agents Total)

### Layer 01 — Requirements Ingestion & Generation
| Agent | Input | Output |
|---|---|---|
| **PRD Ingestion Agent** | Raw PRD (PDF/DOCX/MD) | Normalized JSON schema |
| **FRD Generation Agent** | Requirements JSON | Formatted FRD with acceptance criteria |
| **ERD Synthesis Agent** | FRD content | Mermaid ERD diagram |

### Layer 02 — Sprint Planning & Jira Orchestration
| Agent | Input | Output |
|---|---|---|
| **Sprint Orchestrator Agent** | Approved FRD | Fibonacci-estimated sprint backlog |
| **Jira Writer Agent** | Sprint backlog | Jira epics, stories, subtasks |
| **Dependency Mapper Agent** | Jira backlog | Blocking/blocked-by relationships |

### Layer 03 — Code Generation & Assignment
| Agent | Input | Output |
|---|---|---|
| **Code Generation Agent** | Jira ticket + ERD | Scaffolded code + unit test stubs |
| **PR Creation Agent** | Feature branch | GitHub PR with full metadata |
| **Defect Detection Agent** | CI/CD webhook | Jira bug ticket with failure log |
| **Assignment Agent** | Ticket + team profiles | Optimal developer assignment |

### Layer 04 — PR Diff Review
| Agent | Input | Output |
|---|---|---|
| **Diff Analyzer Agent** | PR diff | Structured diff analysis JSON |
| **Code Review Agent** | Diff + ACs | Inline PR comments + summary |
| **Approval Gate Agent** | Quality score | Ready / Needs Work status |

### Layer 05 — Executive Voice Dashboard
| Agent | Input | Output |
|---|---|---|
| **Summary Aggregation Agent** | Jira + GitHub + CI/CD | Weekly metrics JSON |
| **Dashboard Rendering Agent** | Metrics JSON | Interactive HTML dashboard |
| **Voice Briefing Agent** | Metrics summary | 10-min MP3 briefing + transcript |
| **Q&A Routing Agent** | Exec question | Slack/email to PM or assignee |

---

## 📋 Product Requirements Documents

Full PRDs for all 5 layers are included in this repository:

| PRD | Layer | Contents |
|---|---|---|
| [PRD-01](./docs/PRD-01-Requirements-Ingestion.md) | Requirements Ingestion | Goals, agent architecture, functional & non-functional requirements |
| [PRD-02](./docs/PRD-02-Sprint-Planning.md) | Sprint Planning & Jira | Orchestration logic, Jira API integration specs |
| [PRD-03](./docs/PRD-03-Code-Generation.md) | Code Generation & Assignment | Coding agents, PR creation, defect detection |
| [PRD-04](./docs/PRD-04-PR-Review.md) | PR Diff Review | Quality gate logic, review agent design |
| [PRD-05](./docs/PRD-05-Exec-Dashboard.md) | Executive Dashboard | Voice briefing, Q&A routing, exec UX |

---

## 🔌 API Integration

All agents communicate through the Anthropic `/v1/messages` endpoint:

```javascript
const response = await fetch("https://api.anthropic.com/v1/messages", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    model: "claude-sonnet-4-20250514",
    max_tokens: 1000,
    system: AGENT_SYSTEM_PROMPT,   // Agent-specific instructions
    messages: [
      { role: "user", content: agentInput }
    ]
  })
});
```

Each agent has a dedicated **system prompt** that defines its role, input contract, output format, and reasoning constraints. System prompts are version-controlled and configurable per team.

---

## 📊 Projected Impact

| Metric | Before FlowForge AI | After FlowForge AI |
|---|---|---|
| PRD → Jira backlog time | 2–3 days | < 10 minutes |
| Sprint planning ceremony | 3–4 hours | < 45 minutes |
| First PR review turnaround | 8+ hours | < 3 minutes |
| Pre-merge defect catch rate | Baseline | +30% improvement |
| Weekly exec status prep | 2–4 hours engineering time | Fully automated |
| Executive briefing duration | 30-minute meeting | 10-minute voice brief |

---

## 🏗️ Technical Stack (Conceptual)

| Component | Technology |
|---|---|
| **AI Agent Engine** | Anthropic Claude API (`claude-sonnet-4-20250514`) |
| **Orchestration** | LangGraph-style agent graph (node-per-agent) |
| **Sprint Management** | Jira Cloud REST API v3 |
| **Source Control** | GitHub / GitLab (PR hooks + webhooks) |
| **CI/CD Integration** | GitHub Actions / Jenkins webhook events |
| **ERD Rendering** | Mermaid.js |
| **Voice Synthesis** | ElevenLabs API |
| **Dashboard** | React + Recharts, published to exec portal |
| **Notifications** | Slack API + Email |

---

## 🔐 Governance & Human-in-the-Loop

FlowForge AI is designed with **human oversight at every critical gate:**

1. **FRD Review Gate** — PM approves FRD before sprint planning begins
2. **Sprint Commitment Gate** — Team confirms sprint backlog before Jira tickets are created
3. **Code Review Gate** — Agent provides first-pass review; human engineer must approve merge
4. **PR Merge Gate** — No automated merges; all merges require human sign-off
5. **Q&A Routing** — Exec questions routed to humans, not answered by AI directly

> AI accelerates. Humans decide.

---

## 📐 Agentic Design Principles

This project applies key concepts from MIT Applied AI coursework:

- **Specialization over generalization** — Each agent has a single, well-defined responsibility
- **Structured I/O contracts** — Agents communicate via JSON schemas, not freeform text
- **Confidence-aware output** — Low-confidence generations are flagged for human review
- **Feedback loops** — Dismissed agent comments and gate overrides are logged as training signal
- **Graceful degradation** — If an agent fails, the pipeline surfaces the error rather than silently skipping

---

## 📁 Repository Structure

```
flowforge-ai/
├── README.md
├── docs/
│   ├── PRD-01-Requirements-Ingestion.md
│   ├── PRD-02-Sprint-Planning.md
│   ├── PRD-03-Code-Generation.md
│   ├── PRD-04-PR-Review.md
│   └── PRD-05-Exec-Dashboard.md
├── agents/
│   ├── layer01-ingestion/
│   │   ├── prd-ingestion-agent.js
│   │   ├── frd-generation-agent.js
│   │   └── erd-synthesis-agent.js
│   ├── layer02-planning/
│   ├── layer03-execution/
│   ├── layer04-review/
│   └── layer05-reporting/
├── prompts/
│   └── system-prompts/         # Agent system prompt templates
├── schemas/
│   └── io-contracts/           # JSON I/O schemas per agent
└── demo/
    └── mock-data/              # Sample PRDs, FRDs, sprint data
```

---

## 🚀 Getting Started (Demo Mode)

```bash
# Clone the repo
git clone https://github.com/yourusername/flowforge-ai.git
cd flowforge-ai

# Install dependencies
npm install

# Set your Anthropic API key
export ANTHROPIC_API_KEY=your_key_here

# Run the demo pipeline with sample PRD
node demo/run-pipeline.js --input demo/mock-data/sample-prd.md
```

---

## 📣 LinkedIn Post

This project was published as a LinkedIn carousel post demonstrating AI-native SDLC orchestration. The carousel and full architecture diagram are available in the `/assets` folder.

---

## 👤 Author

Built to demonstrate systems-level AI architecture and agentic workflow design, grounded in MIT Applied AI coursework and real-world engineering team experience.

**Connect on LinkedIn** | **Star this repo** | **Drop a comment on the post**

---

## 📄 License

MIT License — feel free to fork, extend, and build on this concept.

---

*FlowForge AI is a conceptual demo. It is not a production system. All projected metrics are estimates based on industry benchmarks and team experience.*
