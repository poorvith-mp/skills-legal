---
name: legal-documents
last_reviewed: 2026-09-06
group: Product and website
description: Draft and review terms of service, DPAs, and cookie notices for your jurisdictions. For GDPR compliance, see data-privacy. Use when drafting website terms of service or privacy policies.
---

# legal-documents

## Core Philosophy
Website legal documents—Terms of Service (ToS), Privacy Policies, Acceptable Use Policies (AUP), and Data Processing Agreements (DPA)—are not boilerplate legalese to copy and paste from another SaaS website. A stolen or generic privacy policy exposes you to statutory fines, while a poorly drafted Terms of Service leaves you defenseless against class-action lawsuits, unpaid chargebacks, and abusive automated scraping. Production legal documents are precise operational contracts tailored to your exact tech stack and regulatory footprint.

---

## 4-Step SaaS Legal Document Architecture

### Step 1: The SaaS Terms of Service (ToS) Architecture
1. **Essential Contractual Shields**:
   - *Binding Agreement & Acceptance*: Enforce clickwrap agreements (user must affirmatively click "I agree to Terms" on signup; browsewrap is frequently unenforceable).
   - *Account Responsibility & Security*: User is solely responsible for maintaining credential security and all actions under their API keys.
   - *Dispute Resolution & Mandatory Arbitration*: Binding individual arbitration under AAA or JAMS rules with an explicit **Class Action Waiver**.
   - *Disclaimer of Warranties & "As-Is" Provision*: Explicit disclaimer of implied warranties of merchantability and fitness for a particular purpose.
   - *Limitation of Liability (LoL)*: Cap aggregate liability to greater of $100 or fees paid in preceding 12 months.

### Step 2: Regulatory Privacy Policy Architecture
1. **Statutory Transparency Requirements (GDPR / CCPA / CalOPPA)**:
   - What data is collected: Explicitly list categories (Contact data, device telemetry, cookies, billing info).
   - How data is used: Service delivery, analytics, billing, security monitoring.
   - Sharing & Third Parties: Disclose categories of service providers (Cloud host, payment gateway, analytics).
   - User Privacy Rights: Clearly explain how users can submit DSAR requests to access, rectify, or delete their personal data.
   - California CPRA Disclosures: "Do Not Sell or Share My Personal Information" link and disclosure of automated decision-making.

### Step 3: Acceptable Use Policy (AUP) & Platform Abuse Defense
1. **Enforcing Platform Boundaries**:
   - Prohibit reverse engineering, decompiling, or probing vulnerability without written authorization.
   - Explicitly ban abusive scraping, denial of service (DoS), spamming, and utilizing the API to build a competing model or service.
   - Immediate suspension rights: Reserve unilateral right to suspend accounts violating AUP with zero advance notice.

### Step 4: The Data Processing Agreement (DPA) & Subprocessor Roster
1. **B2B Enterprise Compliance (GDPR Art. 28)**:
   - For B2B products processing customer personal data, provide a standardized DPA.
   - Incorporate the European Commission's Standard Contractual Clauses (SCCs) for cross-border transfers.
   - Maintain a publicly accessible, up-to-date **Subprocessor List** (`/legal/subprocessors`) with an automated email subscription alert when new subprocessors are onboarded.

---

## Deliverable Format: SaaS Master Terms of Service Template (`TERMS-OF-SERVICE.md`)

```markdown
# Terms of Service: [Company / Platform Name]
*Last Updated: [YYYY-MM-DD] | Effective Date: [YYYY-MM-DD]*

## 1. Agreement to Terms
By creating an account or accessing [Platform Name] ("Service"), you agree to be bound by these Terms of Service. If you do not agree, do not access the Service.

## 2. Acceptable Use & API Restrictions
You agree not to:
- Reverse engineer, decompile, or extract source code from the Service.
- Use automated scrapers or bots to extract data without express written permission.
- Use outputs from the Service to train or benchmark competing machine learning models.
- Exceed documented API rate limits or interfere with service integrity.

## 3. Limitation of Liability & Warranty Disclaimer
THE SERVICE IS PROVIDED "AS IS" AND "AS AVAILABLE." TO THE MAXIMUM EXTENT PERMITTED BY LAW, [COMPANY] DISCLAIMS ALL WARRANTIES, EXPRESS OR IMPLIED. IN NO EVENT SHALL [COMPANY]'S AGGREGATE LIABILITY EXCEED THE TOTAL AMOUNT PAID BY YOU IN THE TWELVE (12) MONTHS PRECEDING THE CLAIM.

## 4. Dispute Resolution & Class Action Waiver
ANY DISPUTE ARISING UNDER THESE TERMS SHALL BE RESOLVED BY BINDING INDIVIDUAL ARBITRATION UNDER THE RULES OF THE AMERICAN ARBITRATION ASSOCIATION (AAA). YOU EXPRESSLY WAIVE ANY RIGHT TO PARTICIPATE AS A PLAINTIFF OR CLASS MEMBER IN ANY CLASS OR REPRESENTATIVE PROCEEDING.

## 5. Contact Information
Legal inquiries: `legal@[domain].com` | Address: [Corporate Physical Address]
```

---

## Worked Example: Defending Against Reverse Engineering via ToS

- **Incident**: A competitor signed up for a starter plan and began scraping thousands of API responses to distill a competing AI model.
- **Action**: Company invoked Section 2 (Acceptable Use: prohibition on training competing models).
- **Result**: Instantly terminated competitor account, blocked IP ranges, and issued a formal cease-and-desist letter citing breach of contract. Competitor complied and deleted distilled dataset.

---

## Verification Checklist

- [ ] Terms of Service enforce clickwrap acceptance on signup.
- [ ] Class action waiver and binding individual arbitration clauses are included.
- [ ] Privacy Policy details all data collected, lawful bases, and DSAR contact mechanics.
- [ ] Acceptable Use Policy prohibits automated scraping, model distillation, and reverse engineering.
- [ ] B2B DPA includes EU Standard Contractual Clauses (SCCs) and active subprocessor roster.

---

## Anti-Patterns

- **Browsewrap Assumptions**: Hiding a tiny link in the footer and assuming visitors are legally bound without affirmative agreement.
- **Copy-Pasting from Competitors**: Copying another company's Terms of Service, including references to products and jurisdictions that don't apply to you.
- **Missing Dispute Resolution**: Leaving agreements open to class-action litigation in adverse jurisdictions.
