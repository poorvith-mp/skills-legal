---
name: ai-governance
group: Compliance
description: Design responsible-AI policy, model risk assessment, bias auditing and EU AI Act controls. For code audits, see model-audit. Use when designing responsible-AI policies or compliance.
---

# ai-governance

## Core Philosophy
AI Governance is not a collection of vague corporate ethical declarations posted to a marketing website. As the European Union AI Act, US NIST AI Risk Management Framework (AI RMF 1.0), and sectoral regulators (FTC, SEC, FDA) take statutory effect, AI governance is a binding legal and architectural engineering mandate. AI systems require rigorous classification of risk tiers, technical conformity documentation, automated bias auditing, continuous human-in-the-loop (HITL) oversight mechanisms, and fail-closed safety guardrails.

---

## 4-Step Legal & Technical AI Governance Framework

### Step 1: Regulatory Risk Tiering & Scope Classification
1. **EU AI Act Risk Classification**:
   - *Unacceptable Risk (Prohibited)*: Social scoring, cognitive behavioral manipulation, real-time biometric identification in public spaces (Immediate ban).
   - *High-Risk*: AI used in critical infrastructure, recruitment/employment decisioning, credit scoring, law enforcement, or essential public services. Requires full conformity assessment under Chapter 2.
   - *General-Purpose AI (GPAI)*: Foundation models (e.g. LLMs). Models with cumulative compute $> 10^{25}$ FLOPs face systemic risk obligations (mandatory red-teaming, energy efficiency reporting, model evaluation).
   - *Minimal / Non-High Risk*: Standard customer support chatbots, spam filters, recommendation feeds (Transparency obligations apply: users must be informed they are interacting with AI).
2. **NIST AI RMF 1.0 Alignment**:
   - Structure governance into four operational functions: **Govern** (organizational culture), **Map** (context and threat modeling), **Measure** (quantitative metrics and evals), and **Manage** (continuous incident response).

### Step 2: Technical Conformity Documentation (Annex IV Mandate)
1. **The Technical Documentation Dossier**:
   - For high-risk or commercial GPAI systems, maintain an up-to-date compliance dossier:
     - Detailed system architecture diagram and component dependencies.
     - Training data provenance: legal basis for scraping, copyright licensing agreements, data cleansing procedures.
     - Validation and testing metrics: disaggregated performance across demographic cohorts.
     - Known limitations, failure modes, and unintended behavior logs.

### Step 3: Bias Auditing, Fair Lending & Non-Discrimination
1. **Quantitative Algorithmic Auditing**:
   - Calculate Disparate Impact Ratio (DIR) and Equalized Odds across protected classes (Race, Gender, Age, Disability).
   - Four-Fifths Rule compliance: Selection rate for any protected group must not be $< 80\%$ of the highest group's rate in employment or credit decisioning.
2. **Third-Party Independent Audits**:
   - Schedule annual independent adversarial red-teaming and bias audits (e.g., fulfilling NYC Local Law 144 requirements for automated employment tools).

### Step 4: Human-in-the-Loop (HITL) & Incident Reporting
1. **Meaningful Human Oversight**:
   - Design interfaces where human operators can effectively override, intervene, or halt the AI output before it produces a legally binding decision.
2. **Statutory Serious Incident Reporting**:
   - Establish an incident response protocol to notify relevant market surveillance authorities within **72 hours** of detecting an AI incident causing severe harm or fundamental rights violations.

---

## Deliverable Format: AI Governance & Conformity Specification (`AI-GOVERNANCE-SPEC.md`)

```markdown
# AI Regulatory Governance & Conformity Spec: [System Name]

## 1. System Classification & Legal Scope
- **System Name & Model Checkpoint**: [e.g. CandidateRanker v2.4 (Fine-tuned Mistral-7B)]
- **Primary Business Use Case**: Automated candidate resume pre-screening
- **EU AI Act Risk Tier**: **HIGH-RISK** (Annex III: Employment & Worker Management)
- **NIST AI RMF Status**: Map & Measure completed; Manage operational

## 2. Training Data Provenance & Copyright Compliance
- **Training Corpus**: 250,000 anonymized internal historical applications (2020–2025)
- **Lawful Basis (GDPR)**: Legitimate Interest with documented balancing test
- **Copyright Attestation**: Zero unlicensed copyrighted text or scraped third-party data

## 3. Algorithmic Bias Audit Results (NYC Local Law 144)
| Demographic Cohort | Selection Rate | Disparate Impact Ratio (DIR) | Compliance Status |
|---|---|---|---|
| Female Applicants | 22.4% | 0.88 | COMPLIANT (>= 0.80) |
| Male Applicants | 25.5% | 1.00 (Reference) | COMPLIANT |
| Minority Ethnic Group | 21.8% | 0.85 | COMPLIANT (>= 0.80) |

## 4. Human Oversight & Kill-Switch Architecture
- **Human-in-the-Loop Protocol**: AI produces recommendations only; final interview selection requires affirmative click by Human Recruiter.
- **Circuit Breaker**: If daily disparity ratio deviates > 15%, automated screening halts immediately and alerts `#compliance-legal`.
```

---

## Worked Example: Recruitment AI Bias Remediation

- **Context**: SaaS platform developed an AI model to rank software engineering applicants.
- **Audit Finding**: Model was penalizing resumes containing the phrase "women's chess club captain" due to historical gender imbalance in engineering training data.
- **Remediation**: Stripped non-job-related extracurricular identifiers from feature preprocessing; balanced training loss with demographic parity constraints.
- **Result**: NYC Local Law 144 compliance certificate issued; DIR improved from 0.71 to 0.92.

---

## Verification Checklist

- [ ] AI system is classified into its statutory risk tier (EU AI Act / NIST).
- [ ] Training data provenance and copyright licensing are documented in an audit dossier.
- [ ] Disparate Impact Ratio and fairness metrics meet regulatory thresholds ($\ge 0.80$).
- [ ] Human-in-the-loop override controls are architected into the software interface.
- [ ] 72-hour serious incident reporting protocol is established with compliance counsel.

---

## Anti-Patterns

- **Deploying High-Risk AI as "Beta"**: Assuming experimental tags exempt high-risk systems from legal liability.
- **Black-Box Decisioning**: Firing employees or denying credit based on AI scores without providing human-readable explanations.
- **Ignoring Data Provenance**: Fine-tuning proprietary commercial models on pirated books or unvetted web scrapes.
