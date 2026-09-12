---
name: company-formation
last_reviewed: 2026-09-06
group: Company
description: Choose the entity, handle incorporation, founder agreements, and vesting schedules. For tax modeling, see tax-strategy. Use when incorporating Delaware C-Corps or 83(b) filings.
---

# company-formation

## Core Philosophy
Forming a company is not a hasty online form submission to get a logo on an invoice. For technology startups and venture-scale software companies, corporate formation is the foundational legal structure governing equity ownership, tax liability, intellectual property protection, and investor capital injection. Setting up the wrong entity type or failing to file critical tax elections (such as IRS Section 83(b)) can trigger catastrophic personal tax bills and destroy future venture financing.

---

## 4-Step Startup Corporate Formation Discipline

### Step 1: Entity Selection: Delaware C-Corp vs LLC
1. **The Venture-Backed Standard (Delaware C-Corporation)**:
   - Mandatory if you plan to raise venture capital, issue stock options to employees (Incentive Stock Options - ISOs), or qualify for **QSBS** (Qualified Small Business Stock, Section 1202, allowing up to $10M in federal tax-free capital gains).
   - Delaware provides the Court of Chancery (specialized corporate law judges, predictable legal precedent).
2. **The Bootstrapped / Cash-Flow Alternative (LLC)**:
   - Ideal for single-owner lifestyle businesses, local agencies, or real estate assets where pass-through taxation avoids corporate double taxation.

### Step 2: Incorporation & Stock Authorization Architecture
1. **Certificate of Incorporation (DE Secretary of State)**:
   - *Authorized Shares*: Standard venture setup is **10,000,000 shares of Common Stock**.
   - *Par Value*: Set par value to **$0.00001 per share** (prevents massive Delaware franchise tax bills calculated on assumed par value).
2. **Initial Board Consents & Bylaws**:
   - Adopt standard Corporate Bylaws.
   - Initial Director consents appointing corporate officers (President/CEO, Secretary, Treasurer).

### Step 3: Founder Stock Purchase Agreements & Vesting
1. **The 4-Year Vesting Standard**:
   - Never issue 100% upfront unconditional stock to co-founders.
   - Enforce standard **4-year vesting with a 1-year cliff**:
     - 0% vested during months 1–12.
     - 25% vests on the exact 1-year anniversary of the Vesting Commencement Date.
     - Remaining 75% vests monthly in equal increments over the subsequent 36 months ($1/48text{th}$ per month).
2. **Acceleration Triggers (Single vs Double Trigger)**:
   - *Single Trigger*: Immediate full vesting upon company acquisition (Investors hate this; leads to founder walk-aways).
   - *Double Trigger (Market Standard)*: Acceleration occurs *only* if the company is acquired **AND** the founder is terminated without cause or resigns for good reason within 12 months post-sale.

### Step 4: The Mandatory IRS Section 83(b) Election Filing
1. **The 30-Day Hard Statutory Deadline**:
   - An 83(b) election notifies the IRS that you elect to pay income tax on the fair market value of unvested stock *today* (when value is $0.00001/share) rather than paying ordinary income tax on the appreciated value as each monthly chunk vests over 4 years.
   - **Deadline**: Must be physically filed with the IRS within **strictly 30 calendar days** of the stock purchase date. No extensions or late relief exist under any circumstances.
2. **Proof of Filing Discipline**:
   - Send via USPS Certified Mail with Return Receipt Requested. Keep certified tracking receipt, signed letter, and copy of IRS transmittal permanently in corporate records.

---

## Deliverable Format: Corporate Formation Checklist (`FORMATION-CHECKLIST.md`)

```markdown
# Corporate Formation & Governance Checklist: [Company Name]

## 1. Corporate Entity Structure
- **Entity Type**: Delaware C-Corporation
- **Authorized Capital**: 10,000,000 shares Common Stock ($0.00001 par value)
- **Delaware Registered Agent**: [Name, Address]
- **EIN (Employer Identification Number)**: [XX-XXXXXXX]

## 2. Founder Stock Allocation & Vesting Matrix
| Founder Name | Shares Issued | % Total Common | Vesting Schedule | Cliff Date | 83(b) Filed Date | USPS Tracking # |
|---|---|---|---|---|---|---|
| [Founder 1] | 5,500,000 | 55% | 4-Year / 1-Yr Cliff | [YYYY-MM-DD] | [YYYY-MM-DD] | [7020 XXXX...] |
| [Founder 2] | 4,500,000 | 45% | 4-Year / 1-Yr Cliff | [YYYY-MM-DD] | [YYYY-MM-DD] | [7020 XXXX...] |

## 3. Core Corporate Documents Required
- [x] Certificate of Incorporation (Delaware stamped copy)
- [x] Action by Sole Incorporator
- [x] Corporate Bylaws adopted
- [x] Founder Stock Purchase Agreements signed
- [x] Confidential Information and Invention Assignment Agreements (CIIAA) signed
- [x] IRS Section 83(b) Election forms mailed via Certified Mail
```

---

## Worked Example: The $200,000 83(b) Tax Disaster Prevented

- **Scenario**: Two founders incorporated a C-Corp and purchased 5M shares each for $50.
- **Execution**: Both founders immediately mailed signed Section 83(b) elections via Certified Mail to the IRS on Day 8 post-incorporation.
- **Payoff**: Two years later, the company raised a Series A at a $20M valuation ($2/share). Because 83(b) was filed, the founders paid $0 in income tax on vesting shares. Had they forgotten the 83(b), each founder would have owed over $200,000 in personal ordinary income tax on phantom paper stock gains.

---

## Verification Checklist

- [ ] Delaware Certificate of Incorporation sets par value to $0.00001 per share.
- [ ] Founder Stock Purchase Agreements enforce 4-year vesting with a 1-year cliff.
- [ ] Double-trigger acceleration is specified (avoiding investor-unfriendly single trigger).
- [ ] Proprietary Information and Invention Assignment Agreements (CIIAA) executed by all founders.
- [ ] IRS Section 83(b) elections mailed via USPS Certified Mail within 30 days of stock grant with tracking retained.

---

## Anti-Patterns

- **Missing the 30-Day 83(b) Deadline**: Waiting until tax season in April to think about 83(b), triggering immense personal tax liabilities on unvested equity.
- **Handshake Equity Splits**: Working for 18 months without formal incorporation or signed stock purchase agreements.
- **Unvested 50/50 Grants**: Giving a co-founder 50% equity upfront on day 1 with zero vesting, watching them quit 2 months later and keep half the company.
