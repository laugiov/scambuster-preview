# ScamBuster

**A Research Laboratory for Automated Scambaiting & Threat Intelligence**

![Status](https://img.shields.io/badge/status-private_preview-blue)
![Stack](https://img.shields.io/badge/stack-PHP%208.3%20|%20Symfony%207%20|%20PostgreSQL%20|%20LLM-green)
![Tests](https://img.shields.io/badge/tests-955%20passing-brightgreen)
![License](https://img.shields.io/badge/license-code%20private%20|%20docs%20CC%20BY--NC--SA-lightgrey)

> **Last updated**: 2025-12-17 | **Data period**: November-December 2025

---

## The Problem: Billions Lost Annually to Email Scams

Every day, billions of scam emails are sent worldwide. Traditional defenses simply block and forget—providing **zero intelligence** about attacker infrastructure, financial channels, or campaign attribution.

> **Industry estimates**: ~3.4B daily scam emails (Statista 2024), $12.5B annual losses (FBI IC3 2023). See [Problem Statement](docs/01_problem_statement.md) for sourced figures.

**The result:**
- Scammers pivot immediately to new targets
- No deterrent effect (scamming remains low-risk, high-reward)
- Security teams lack visibility into emerging threats
- The same infrastructure continues operating for months

> **What if every scam email could become a source of threat intelligence?**

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

### Validation Dataset

| Metric | Value |
|--------|-------|
| **Synthetic conversations** | 2,221 |
| **Statistical significance** | p < 0.001 (Welch's t-test) |
| **Convergence coefficient** | CV = 0.1703 |
| **Effect size** | Cohen's d = 0.37 |

### Key Discoveries

**Persona Performance Varies 5.5× by Scam Type**

The adaptive system discovered that:
- `elderly_person` persona achieves **48.7h max engagement** (vs 0.3h median)
- Optimal persona differs significantly across scam types
- Human intuition about "best" strategies is often wrong
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

### Adaptive Learning (Research Innovation)

**Novel application of contextual multi-armed bandits to scambaiting.** To our knowledge, this is among the earliest documented implementations combining RL-based persona selection with automated honeypot engagement in a production-oriented, measurable setup.

| Aspect | Implementation |
|--------|----------------|
| **Algorithm** | ε-greedy (V1) → Thompson Sampling (V2) |
| **Context** | 1 bandit per scam type |
| **Arms** | 13 personas × 13 scam types = 169 combinations |
| **Reward** | 40% duration + 25% IOCs + 25% high-value IOCs + 10% completion |
| **Convergence** | <100 sessions per scam type |

The system **learns automatically** which conversational strategies work best, without human intervention.

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

- No scambaiting prompts or persona definitions
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
| **Phase 2**: Adaptive scambaiting (ε-greedy) | ✅ Complete | Nov-Dec 2025 |
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
| **Name** | Laurent Giovannoni |
| **LinkedIn** | [linkedin.com/in/giovannonilaurent](https://linkedin.com/in/giovannonilaurent) |
| **Context** | E-MSc Cybersecurity — Master's Thesis |
| **Security** | security@scambuster.io (for responsible disclosure) |

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
3. **Scientific**: Empirically validated adaptive scambaiting (p < 0.001, N=2,221)
4. **Practical**: Demonstrated efficiency at pilot scale (€0.52 for 2,213 IOCs)

### Citation

```bibtex
@mastersthesis{giovannoni2025scambuster,
  author = {Giovannoni, Laurent},
  title = {ScamBuster: Adaptive Scambaiting via Multi-Armed Bandits
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
  <strong>Transforming scam threats into threat intelligence through adaptive AI</strong>
</p>

<p align="center">
  <a href="docs/01_problem_statement.md">Learn More</a> •
  <a href="#request-access">Request Demo</a> •
  <a href="docs/06_roadmap.md">View Roadmap</a>
</p>
