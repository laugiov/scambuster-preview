# ScamBuster

**A Defensive Engagement & Threat Intelligence Research Laboratory (Email-first)**

![Status](https://img.shields.io/badge/status-private_preview-blue)
![Stack](https://img.shields.io/badge/stack-PHP%208.3%20|%20Symfony%207%20|%20PostgreSQL%20|%20LLM-green)
![Tests](https://img.shields.io/badge/tests-955%20passing-brightgreen)
![License](https://img.shields.io/badge/license-code%20private%20|%20docs%20CC%20BY--NC--SA-lightgrey)

> **Last updated**: 2025-12-17 | **Data period**: November-December 2025

ScamBuster turns inbound scam emails into **actionable threat intelligence** through **controlled, policy-driven engagement**.

The project serves defensive security, fraud prevention, and applied research purposes (not offensive use). It extracts IOCs, maps campaigns, measures engagement effectiveness, and exports intelligence in STIX/MISP formats. All workflows are safety-gated, cost-aware, and fully auditable.

> This repository is a **public preview** (documentation only). Operational assets remain private to prevent misuse.

---

## The Problem: Email Scams Are High-Volume, and Mostly "Invisible" to Defenders

Email scams operate at massive scale. Most security programs are forced into a **block-and-forget** posture: the message is removed, but the attacker infrastructure, financial rails, and campaign signals remain largely unobserved. Industry estimates and sourced figures are documented in [Problem Statement](docs/01_problem_statement.md).

This creates a structural gap. There is little to no attribution across messages and campaigns, limited visibility into evolving TTPs and infrastructure reuse, and slow feedback loops on what actually works. Most organizations miss opportunities to generate intelligence from real-world interaction with threat actors.

ScamBuster explores this gap by converting scam emails into measurable threat intelligence, safely and at scale.

---

## ScamBuster: From Blocking to Understanding

ScamBuster is a **research laboratory** that transforms email scams into actionable intelligence through controlled AI engagement.

### The Vision: A Scam Observatory

Instead of discarding scam emails, ScamBuster creates an **observatory** that answers critical questions:

| Question | ScamBuster Insight |
|----------|-------------------|
| **What scam types are trending?** | Real-time classification across 13 categories |
| **Which personas maximize engagement?** | Adaptive learning identifies optimal strategies per scam type |
| **What IOCs do scammers reveal?** | Automatic extraction of 34 indicator types |
| **How do campaigns evolve?** | Clustering and attribution over time |
| **What works against different scammers?** | Data-driven optimization, not intuition |

### Three Research Dimensions

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    SCAMBUSTER RESEARCH LABORATORY                        │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐       │
│  │  CONVERSATIONAL  │  │   INTELLIGENCE   │  │    ADAPTIVE      │       │
│  │    LABORATORY    │  │    EXTRACTION    │  │    LEARNING      │       │
│  ├──────────────────┤  ├──────────────────┤  ├──────────────────┤       │
│  │                  │  │                  │  │                  │       │
│  │ Test which       │  │ Analyze how &    │  │ Automatically    │       │
│  │ personas work    │  │ when IOCs are    │  │ optimize         │       │
│  │ best for each    │  │ revealed during  │  │ strategies via   │       │
│  │ scam type        │  │ conversations    │  │ reinforcement    │       │
│  │                  │  │                  │  │ learning         │       │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘       │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## Pilot Results (December 2025)

### Controlled Live Deployment (30 Days)

| Metric | Value | Notes |
|--------|-------|-------|
| **Conversations** | 150 | Real scammers engaged |
| **IOCs Extracted** | 2,213 | Emails, phones, IBANs, crypto wallets |
| **IOC Precision** | 100% on audited sample (N=107) | vs 44% with regex-only baseline |
| **System Uptime** | 30 days | Zero incidents, fully automated |
| **Operational Cost** | €0.52 | Total LLM API cost |
| **Cost per IOC** | €0.0002 | Negligible operational expense |

> **Metrics scope & definitions**
>
> Figures come from **two observation windows** in December 2025:
> - **Extended run (~1 month)**: Used for stability and scale indicators (150 conversations, 2,213 IOCs, 30 days uptime)
> - **Controlled validation run**: Used for ROI analysis and campaign-level attribution
>
> **IOC precision (100%)** = no false positives in audited sample (precision = TP / (TP + FP), N=107 messages).
> Sample-based validation details are documented in [Evaluation Methodology](docs/05_evaluation_methodology.md).

### Validation Summary

Adaptive strategy selection was validated on 2,221 synthetic conversations with statistically significant results (p < 0.001). Full methodology and statistical details are available in [Evaluation Methodology](docs/05_evaluation_methodology.md).

### Key Discoveries

**Strategy Performance Varies Significantly by Scam Type**

The adaptive system discovered that:
- Optimal strategy differs significantly across scam categories
- Human intuition about "best" approaches is often wrong
- Data-driven selection outperforms random assignment

**Campaign Attribution**

From 150 conversations, identified **coordinated operations**:
- Shared infrastructure (same IBANs across conversations)
- Common TTPs (message templates, escalation patterns)
- Geographic clustering (phone number prefixes)

---

## How It Works

### Multi-Agent LLM Architecture

Five specialized AI agents work in concert:

| Agent | Role | Achievement |
|-------|------|-------------|
| **ScamClassifier** | Categorize incoming scams | 82% auto-classification, 13 types |
| **IocExtractor** | Extract threat indicators | 100% precision on audited sample, 34 IOC types |
| **Generator** | Create contextual responses | +35% IOCs post-IBAN detection |
| **Validator** | Ensure safety & quality | 95% approval rate |
| **Orchestrator** | Coordinate & optimize costs | <€0.0002/message |

### Adaptive Strategy Selection (Applied Research)

ScamBuster does not rely on a single fixed "best" conversational approach. Instead, it uses **adaptive strategy selection** to learn, per scam category, which safe persona/response patterns maximize **intelligence yield** under strict constraints.

Strategies are selected based on scam type (BEC, lottery, romance, refund, etc.). The system optimizes for defensive signals such as indicators revealed, validated artifacts, and sustained interaction, while controlling cost and safety. Every response is gated by validation rules and policy checks before being sent. Performance is monitored over time, enabling data-driven iteration rather than intuition.

| Aspect | Summary |
|--------|---------|
| Approach | Contextual bandit / adaptive experimentation |
| Context | One policy per scam category (extensible) |
| Strategy space | Persona & response patterns (kept private to prevent misuse) |
| Objectives | Intelligence yield, safety compliance, and cost efficiency |

---

## Value for Stakeholders

### For SOC/CERT Teams

| Capability | Benefit |
|------------|---------|
| **Automated IOC feeds** | STIX 2.1 / MISP-compatible exports |
| **Campaign attribution** | Link individual scams to organized operations |
| **Early warning** | Identify emerging threats before they scale |
| **Reduced analyst workload** | Automated extraction vs manual review |

### For MSSPs

| Capability | Benefit |
|------------|---------|
| **Differentiation** | Proactive TI service vs reactive blocking |
| **Scalability** | One deployment serves multiple clients |
| **ROI demonstration** | Quantifiable intelligence value |

### For Financial Institutions

| Capability | Benefit |
|------------|---------|
| **BEC detection** | Early identification of business email compromise |
| **Account protection** | Report fraudulent accounts to consortium |
| **Fraud prevention** | Intelligence on active money mule networks |

### For Research

| Capability | Benefit |
|------------|---------|
| **Reproducible methodology** | Published protocol for evaluation |
| **Dataset** | Anonymized corpus (Feb 2026) |
| **Collaboration** | Open platform for strategy experimentation |

---

## Documentation

| Document | Description |
|----------|-------------|
| [Problem Statement](docs/01_problem_statement.md) | The €12.5B scam problem in depth |
| [Value Proposition](docs/02_value_proposition.md) | Technical differentiators and ROI |
| [Architecture](docs/03_high_level_architecture.md) | High-level system design |
| [Security & Ethics](docs/04_security_guardrails.md) | Defensive principles, GDPR, safety |
| [Evaluation](docs/05_evaluation_methodology.md) | Metrics, validation, statistical methods |
| [Roadmap](docs/06_roadmap.md) | Timeline and milestones |
| [FAQ](docs/07_faq.md) | Common questions |

---

## What's NOT Included (Operational Security)

To prevent misuse by adversaries, this repository contains **documentation only**:

- No engagement prompts or persona definitions
- No automation workflows or scripts
- No operational playbooks or tactics
- No real conversation data or scammer identifiers
- No API keys, secrets, or operational configurations
- No information enabling offensive use or replication without governance

---

## Project Status

| Phase | Status | Timeline |
|-------|--------|----------|
| **Phase 1**: Multi-agent LLM architecture | ✅ Complete | Oct-Nov 2025 |
| **Phase 2**: Adaptive engagement (ε-greedy) | ✅ Complete | Nov-Dec 2025 |
| **Phase 3**: Thompson Sampling V2 | ✅ Feature-complete (rollout in progress) | Dec 2025 |
| **Phase 4**: Scale & Dashboards | 🔄 In Progress | Dec 2025 |
| **Phase 5**: A/B Testing | 📅 Planned | Jan 2026 |
| **Phase 6**: Publication & Dataset Release | 📅 Planned | Feb 2026 |

> **Status note**: "Feature-complete" means core functionality is implemented and tested. "Rollout in progress" means gradual activation in production is ongoing. See [Roadmap](docs/06_roadmap.md) for week-by-week detail.

---

## Request Access

### Private Demo (45 min)

**What you'll see:**
- End-to-end flow (ingestion → engagement → extraction → export)
- Live dashboard with convergence visualization
- Sanitized sample outputs and IOC examples

**What we need from you:**
- Your role and organization context
- Specific use case or evaluation criteria
- Any compliance constraints (optional)

> **Eligibility**: Access is granted for defensive security, research, or fraud prevention purposes only. No access for offensive use, scam operations, or purposes that conflict with the project's ethical guidelines.

**Operational boundaries:** The system only responds to scam emails already received and never initiates contact. There is no impersonation of real organizations, brands, or individuals (personas are synthetic role patterns, non-identifying). There is no unauthorized access, no hack-back, and no exploitation of scammer infrastructure.

### Pilot Program

**Evaluate in your environment:**
- Time-boxed deployment (4-8 weeks typical)
- Defined scope and success criteria
- Security and compliance review available
- Integration assessment with existing tools

### Partnership Opportunities

- **SOC/MSSP**: SIEM/SOAR integration pilots
- **Research**: Dataset sharing, methodology validation
- **Commercial**: Enterprise licensing discussions

### Contact

| | |
|---|---|
| **Project lead** | Laurent Giovannoni |
| **LinkedIn** | [linkedin.com/in/giovannonilaurent](https://linkedin.com/in/giovannonilaurent) |
| **Context** | E-MSc Cybersecurity, Master's Thesis |
| **Demo request** | Open a [GitHub Issue](../../issues) (private requests welcome) |
| **Security** | See [SECURITY.md](SECURITY.md) for responsible disclosure |

---

## Technology Stack

| Layer | Technology |
|-------|------------|
| **Backend** | PHP 8.3, Symfony 7, DDD architecture |
| **Database** | PostgreSQL, Redis |
| **LLM** | OpenAI API (GPT-4o-mini) |
| **Orchestration** | n8n workflow automation |
| **Infrastructure** | Docker, GitLab CI |
| **Security** | Industry-standard encryption, secrets management |

---

## Academic Context

### Research Contributions

1. **Methodological**: Reproducible protocol for adaptive honeypot evaluation
2. **Technical**: Multi-agent LLM with double validation (95% approval vs 60-70% baseline)
3. **Scientific**: Empirically validated adaptive engagement (p < 0.001, N=2,221)
4. **Practical**: Demonstrated efficiency at pilot scale (€0.52 for 2,213 IOCs)

### Citation

```bibtex
@master{giovannoni2025scambuster,
  author = {Giovannoni, Laurent},
  title = {ScamBuster: Adaptive Controlled Engagement via Multi-Armed Bandits
           for Automated Threat Intelligence Extraction},
  school = {E-MSc Cybersecurity},
  year = {2025}
}
```

---

## License

- **Documentation**: CC BY-NC-SA 4.0
- **Code**: Private (commercial/research license available)
- **Dataset**: CC BY-NC-SA 4.0 (anonymized, February 2026)

---

<p align="center">
  <a href="docs/01_problem_statement.md">Learn More</a> •
  <a href="#request-access">Request Demo</a> •
  <a href="docs/06_roadmap.md">View Roadmap</a>
</p>
