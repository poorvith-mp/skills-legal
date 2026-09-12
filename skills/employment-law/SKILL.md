---
name: employment-law
last_reviewed: 2026-09-06
group: Company
description: >-
  Get hiring right: contractor vs employee classification, offer terms, and non-competes. Use when
  hiring employees, contractors, or writing offer terms.
---

# employment-law

## Core Philosophy
Employment law mistakes are among the fastest ways to bankrupt a high-growth company. Misclassifying employees as independent contractors, utilizing unenforceable non-compete agreements, or failing to properly execute intellectual property assignment agreements creates catastrophic liabilities for back taxes, overtime penalties, and ruined venture financing due diligence. Professional hiring requires strict legal compliance with classification tests, bulletproof offer terms, and clear separation protocols.

---

## 4-Step Employment Law & Hiring Governance

### Step 1: Worker Classification: Independent Contractor vs Employee
1. **The Legal Classification Tests**:
   - *The IRS 20-Factor Test & DOL Economic Realities*: Focuses on degree of behavioral control, financial control, and integration into core business operations.
   - *The California & Multi-State "ABC" Test*: A worker is presumed an employee unless the company proves **ALL THREE**:
     - **A**: The worker is free from the control and direction of the hiring entity.
     - **B**: The worker performs tasks outside the usual course of the hiring entity's business (e.g. hiring a software dev for a software company fails Prong B).
     - **C**: The worker is customarily engaged in an independently established trade, occupation, or business.
2. **Misclassification Penalties**:
   - Liability for back payroll taxes (FICA, FUTA), unpaid overtime, workers' compensation penalties, and mandatory civil fines.

### Step 2: The Offer Letter & At-Will Employment Architecture
1. **Core Offer Letter Protections**:
   - Explicit **At-Will Employment** statement: Either party may terminate the employment relationship at any time, with or without cause or advance notice.
   - Avoid promissory language implying guaranteed tenure: Never write "annual salary of $150,000 for your first year" (implies a 1-year guaranteed contract); write "an initial base rate of $12,500 per month, payable semi-monthly".
   - Contingencies: Offer is expressly contingent upon background check clearance, proof of legal work authorization (Form I-9), and signed CIIAA.

### Step 3: IP Assignment (CIIAA) & Restrictive Covenants
1. **Confidential Information and Invention Assignment Agreement (CIIAA)**:
   - Mandatory for 100% of employees and contractors prior to day 1.
   - Complete assignment of all inventions, code, designs, and discoveries developed during employment relating to the company's current or prospective business.
   - Require new hires to list all Prior Inventions (carve-outs) on Exhibit A to prevent ownership disputes.
2. **Non-Competes vs Non-Solicitation**:
   - *Non-Competes*: Largely void and legally unenforceable in tech hubs (California, New York, FTC nationwide rules). Do not rely on non-competes.
   - *Non-Solicitation of Customers & Employees*: Enforce reasonable, narrowly tailored non-solicitation clauses (12 months maximum) protecting proprietary customer lists and preventing team poaching.

### Step 4: Separation, Severance & Release of Claims
1. **Risk-Mitigated Termination Protocol**:
   - Deliver final paycheck in accordance with state statutory timelines (e.g. California mandates final paycheck handed over *on the day of termination*, including all accrued PTO).
2. **The Severance Agreement & General Release**:
   - Severance payments must be conditioned upon signing a comprehensive **Release of All Claims**.
   - Older Workers Benefit Protection Act (OWBPA) compliance: For employees age 40+, provide strictly 21 days to consider the agreement (45 days for group layoffs) and 7 days to revoke post-signing.

---

## Deliverable Format: Employment Onboarding & Classification Spec (`EMPLOYMENT-SPEC.md`)

```markdown
# Employment Compliance & Offer Architecture: [Role Title]

## 1. Classification & Compensation Architecture
- **Worker Title**: Senior Backend Engineer
- **Classification**: Exempt Employee (FLSA Computer Professional Exemption) / Non-Exempt / Contractor
- **ABC Test Evaluation**: Prong B requires employee status (Core software development)
- **Compensation**: $14,000 / month ($168,000 annualized base) + 25,000 Stock Options

## 2. Mandatory Offer Letter Clauses
- [x] Unambiguous At-Will Employment disclaimer included.
- [x] Semi-monthly pay rate stated (no annual term guarantees).
- [x] Contingent upon Form I-9 verification and signed CIIAA.

## 3. Proprietary Inventions & Restrictive Covenants
- **CIIAA Status**: Form executed; Exhibit A (Prior Inventions) verified clean.
- **Non-Compete Policy**: Non-compete omitted per FTC/State law; 12-month Non-Solicitation enforced.

## 4. Termination & Final Pay Statutory Requirements
- **Jurisdiction**: California
- **Final Pay Deadline**: Immediate on termination date (including accrued vacation).
- **Severance Release**: Standard ADEA/OWBPA 21-day consideration clause included.
```

---

## Worked Example: Contractor Misclassification Audit Defense

- **Situation**: Startup classified 6 core mobile app developers as 1099 independent contractors to avoid benefits and payroll taxes.
- **Audit Finding**: Developers failed California ABC Test Prong B because building mobile apps is the core business of the mobile app company.
- **Remediation**: Converted workers to W-2 employees with retroactive health benefits and payroll tax withholdings.
- **Outcome**: Successfully passed institutional investor legal due diligence for a $10M Series A financing round without escrow holdbacks.

---

## Verification Checklist

- [ ] Workers pass the ABC test or economic reality test before being classified as 1099 contractors.
- [ ] Offer letters contain explicit At-Will employment language and avoid term guarantees.
- [ ] Confidential Information and Invention Assignment Agreement (CIIAA) signed before first day.
- [ ] Prior inventions are explicitly carved out on Exhibit A of CIIAA.
- [ ] Severance agreements for workers age 40+ provide mandatory 21-day review and 7-day revocation periods.

---

## Anti-Patterns

- **The "Full-Time 1099 Contractor" Myth**: Treating an individual like an employee (set hours, company laptop, managing others) while issuing a 1099 to avoid taxes.
- **Guaranteed Annual Contracts in Offer Letters**: Writing "You are hired for a 1-year contract at $120k", destroying at-will protection.
- **Withholding Final Pay**: Delaying an employee's final paycheck until they return equipment, incurring severe state statutory waiting-time penalties.
