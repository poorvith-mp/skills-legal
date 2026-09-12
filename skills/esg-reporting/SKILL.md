---
name: esg-reporting
last_reviewed: 2026-09-06
group: Compliance
description: >-
  Build ESG reporting: materiality assessment, metrics and disclosure frameworks. Use when
  compiling ESG disclosures, carbon accounting, or sustainability reports.
---

# esg-reporting

## Core Philosophy
Environmental, Social, and Governance (ESG) reporting is transitioning rapidly from voluntary corporate marketing brochures into mandatory, audited statutory disclosure regimes (such as the EU Corporate Sustainability Due Diligence Directive - CSRD, SEC Climate Disclosures, and California SB 253/261). Superficial "greenwashing" claims expose companies to direct regulatory enforcement, litigation, and investor divestment. Rigorous ESG reporting requires double materiality assessments, auditable GHG Protocol greenhouse gas accounting, and transparent governance oversight.

---

## 4-Step ESG Accounting & Reporting Framework

### Step 1: Double Materiality Assessment (CSRD Standard)
1. **The Double Materiality Principle**:
   - *Financial Materiality (Outside-In)*: How external climate, environmental, and social risks affect the company's financial performance, cash flows, and valuation.
   - *Impact Materiality (Inside-Out)*: How the company's operations, products, and value chain impact people and the environment.
2. **Materiality Matrix Prioritization**:
   - Score ESG topics (e.g. Energy Consumption, Data Privacy, Workforce Diversity) across financial and impact axes; disclose topics passing materiality thresholds.

### Step 2: Carbon Accounting & Greenhouse Gas (GHG) Protocol
1. **The 3 Emission Scopes**:
   - *Scope 1 (Direct Emissions)*: Fuel combustion from owned facilities, company vehicles, backup generators.
   - *Scope 2 (Indirect Emissions from Purchased Energy)*: Purchased electricity, heating, and cooling (report using both Location-Based and Market-Based methods).
   - *Scope 3 (Value Chain Emissions - The Tech Reality)*: Typically represents 80–95% of a tech company's footprint:
     - Category 1: Purchased goods and services (Cloud hosting: AWS/GCP/Azure compute).
     - Category 6: Business travel (Flights, rail).
     - Category 7: Employee commuting and remote work energy consumption.

### Step 3: Social & Governance Metrics (S & G)
1. **Social (S) Disclosures**:
   - Pay Equity & Gender Pay Gap analysis.
   - Workplace safety, incident rates, and employee turnover metrics.
   - Supply chain labor audits and human rights compliance (anti-modern slavery).
2. **Governance (G) Disclosures**:
   - Board diversity, independence, and executive compensation linked to sustainability targets.
   - Anti-corruption, whistleblower protections, and data security certifications (SOC 2, ISO 27001).

### Step 4: Verification & Audit-Ready Disclosure Frameworks
1. **Framework Alignment**:
   - Structure disclosures to recognized global standards: **GRI** (Global Reporting Initiative), **SASB** (Software & IT Services Standard), and **TCFD** (Task Force on Climate-related Financial Disclosures).
2. **Limited Assurance Readiness**:
   - Compile raw energy bills, utility receipts, cloud carbon telemetry, and HR databases into an auditable evidence binder for external CPAs.

---

## Deliverable Format: ESG Materiality & Emissions Report (`ESG-REPORT.md`)

```markdown
# ESG Disclosure & Carbon Accounting Report: [Fiscal Year]

## 1. Executive Governance & Materiality
- **Reporting Period**: [YYYY-01-01 to YYYY-12-31]
- **Reporting Frameworks**: CSRD / SASB Software & IT Services / GHG Protocol
- **Board Oversight**: Audit & Sustainability Committee (Quarterly review)

## 2. Greenhouse Gas (GHG) Emissions Inventory (Metric Tons CO2e)
| Scope Category | Emission Source | FY25 Emissions ($t	ext{CO}_2	ext{e}$) | FY26 Emissions ($t	ext{CO}_2	ext{e}$) | % Change |
|---|---|---|---|---|
| Scope 1 | Natural gas & company fleet | 14.2 | 12.8 | -9.8% |
| Scope 2 (Market-Based) | Purchased office electricity | 48.6 | 21.4 | -56.0% (Green tariff) |
| Scope 3 (Cat 1: Cloud) | AWS & GCP cloud compute | 412.0 | 385.0 | -6.5% |
| Scope 3 (Cat 6: Travel)| Air travel & lodging | 84.5 | 92.1 | +9.0% |
| **Total Carbon Footprint** | | **559.3** | **511.3** | **-8.6%** |

## 3. Social Capital & Diversity Metrics
- **Global Workforce Gender Split**: 42% Female / 56% Male / 2% Non-binary
- **Unadjusted Gender Pay Gap**: 3.2% (Target: < 2.0%)
- **Voluntary Annual Turnover**: 8.4% (Industry benchmark: 14%)

## 4. Governance & Cybersecurity Safeguards
- **Compliance Certifications**: SOC 2 Type II, ISO 27001:2022
- **Whistleblower Policy**: Independent third-party anonymous reporting hotline active.
```

---

## Worked Example: Cloud Infrastructure Carbon Reduction

- **Challenge**: SaaS enterprise faced enterprise customer RFPs requiring verified Scope 3 cloud emissions reductions.
- **Action**: Transitioned workloads from fossil-powered AWS regions to regions powered by $\ge 90\%$ carbon-free energy (e.g. AWS `eu-north-1` Stockholm and `us-west-2` Oregon). Optimized ARM-based Graviton compute instances.
- **Outcome**: Slashed annual Scope 3 cloud carbon emissions by 44%; unlocked $2.4M in enterprise sales requiring strict ESG supplier standards.

---

## Verification Checklist

- [ ] Materiality assessment evaluates both financial materiality and operational impact.
- [ ] GHG Protocol Scopes 1, 2, and 3 are calculated with documented methodology.
- [ ] Cloud computing emissions are tracked using actual provider carbon APIs.
- [ ] Gender pay equity and workforce diversity statistics are verified against HR records.
- [ ] Report references primary evidence binders prepared for external audit assurance.

---

## Anti-Patterns

- **Greenwashing Superlatives**: Declaring a company "100% Carbon Neutral" based exclusively on unverified, cheap forestry offsets.
- **Ignoring Scope 3**: Software companies omitting cloud hosting and travel emissions, which constitute 90% of their actual footprint.
- **Unverified Marketing Claims**: Publishing environmental claims without underlying audit trails.
