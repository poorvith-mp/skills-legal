---
name: contract-review
last_reviewed: 2026-09-06
group: Contracts
description: >-
  Read someone else's paper: explain clauses plainly, flag the risk and propose amendments that
  protect you. Use when reviewing third-party contracts, vendor paper, or redlining clauses.
---

# contract-review

## Core Philosophy
Reviewing a third-party contract or enterprise vendor paper is not about correcting typos or arguing over stylistic grammar. Redlining contracts is a risk management triage. Enterprise software agreements are inherently biased in favor of the drafting party—loaded with asymmetric indemnities, uncapped liability traps, unilateral termination rights, and aggressive intellectual property captures. A master contract review identifies and neutralizes deal-killing risks while preserving commercial momentum.

---

## 4-Step Contract Review & Redlining Playbook

### Step 1: The 4 Deal-Killer Clauses (P0 Risk Audit)
1. **Limitation of Liability (LoL)**:
   - *The Danger*: Unlimited liability, or asymmetric caps where you are exposed to millions while the vendor's liability is capped at $100.
   - *The Fix*: Enforce a **mutual aggregate cap** equal to fees paid in the preceding 12 months. Ensure uncapped exceptions are strictly limited to gross negligence, willful misconduct, and third-party IP indemnification.
2. **Indemnification (Defense & Hold Harmless)**:
   - *The Danger*: Broad indemnification requiring you to defend the counterparty for "any and all losses arising from your use of the software".
   - *The Fix*: Narrow vendor indemnity to third-party intellectual property infringement claims. Restrict customer indemnity to customer's breach of acceptable use or unlawful customer data.
3. **Intellectual Property & Feedback Capture**:
   - *The Danger*: Overly broad "Feedback" clauses stating that any suggestions, bug reports, or modifications you provide become the exclusive property of the vendor.
   - *The Fix*: Grant a non-exclusive, royalty-free license to use feedback, while expressly retaining all right, title, and interest in your own proprietary software, data, and workflows.
4. **Data Ownership & Privacy**:
   - Ensure you retain 100% ownership of all Customer Data. Prohibit vendor from using your data to train general foundation AI models without explicit opt-in.

### Step 2: Commercial & Operational Trap Audit (P1 Issues)
1. **Termination for Convenience & Auto-Renewal**:
   - Check auto-renewal notice windows: Redline 90-day surprise auto-renewal traps down to 30 days, with mandatory advance written notice from vendor.
   - Require pro-rata refunds of prepaid fees upon vendor termination for convenience or uncured material breach.
2. **Payment Terms & Audit Rights**:
   - Redline aggressive 15-day payment terms to standard Net 30.
   - Limit vendor audit rights to once annually during normal business hours with at least 30 days prior written notice.

### Step 3: The Plain-English Redline Markup Standard
1. **Redline Tone & Professionalism**:
   - Never write abrasive marginal comments. Frame amendments around fairness, industry standards, and mutual risk-sharing:
     - *"Mutualizing this clause to reflect standard market practice."*
     - *"Clarifying that Customer retains ownership of all proprietary data."*
2. **Propose Drop-In Replacement Text**:
   - Always strike out offending text and supply the exact replacement wording in track changes.

### Step 4: Final Risk Memo & Escalation
1. **Synthesize Findings for the Decision Maker**:
   - Categorize redlines into: **High Risk (Walk-Away Blockers)**, **Medium Risk (Commercial Negotiation)**, and **Low Risk (Acceptable Business Risk)**.

---

## Deliverable Format: Contract Redline & Risk Review Memo (`CONTRACT-REVIEW.md`)

```markdown
# Contract Review & Redline Memo: [Vendor / Client Paper]

## 1. Executive Summary & Risk Classification
- **Agreement Reviewed**: Master Services Agreement (Vendor Paper)
- **Counterparty**: [Counterparty Name]
- **Contract Value**: [$XX,XXX ARR]
- **Overall Risk Rating**: **MEDIUM-HIGH** (Requires 3 critical redlines prior to signature)

## 2. P0 Critical Issues (Deal Killers)
| Section # | Clause Name | Identified Risk | Proposed Redline Amendment | Counterparty Justification |
|---|---|---|---|---|
| Sec 8.2 | Limitation of Liability | Unilateral cap protecting vendor only ($1,000) | Strike clause; insert mutual 12-month trailing fee aggregate cap | "Standard market practice requires mutual limitation of liability." |
| Sec 10.1 | IP Indemnity | Customer must indemnify vendor for all third-party claims | Remove customer obligation; restrict to vendor IP defense | "Vendor must warrant that its own software does not infringe 3rd-party IP." |

## 3. P1 Operational & Commercial Risks
- **Auto-Renewal (Sec 4.3)**: Redline 60-day auto-renewal notice to 30 days with required vendor email reminder.
- **Payment Terms (Sec 5.1)**: Change "Due upon receipt" to "Net 30 days".
- **AI Model Training (Sec 12.4)**: Add express prohibition: *"Vendor shall not use Customer Data to train, fine-tune, or improve general AI models."*

## 4. Negotiation Strategy & Recommendation
Approve signature strictly subject to counterparty accepting Section 8.2 (Mutual LoL) and Section 12.4 (AI Training Prohibition).
```

---

## Worked Example: Neutralizing an Uncapped SaaS Indemnity

- **Original Clause**: *"Customer agrees to defend, indemnify, and hold harmless Vendor from and against any losses, damages, or costs arising out of Customer's use of the Service."*
- **The Redline**: Struck "use of the Service"; replaced with *"Customer's material breach of this Agreement or violation of applicable law."* Added mutual vendor IP infringement indemnity.
- **Outcome**: Vendor accepted redlines within 24 hours; customer saved from potential multi-million dollar liability for vendor platform bugs.

---

## Verification Checklist

- [ ] Limitation of Liability is mutual and capped at 12 months trailing fees.
- [ ] Consequential and punitive damages are waived by both parties.
- [ ] Customer Data ownership is unequivocally retained with AI training prohibited.
- [ ] Auto-renewal traps are modified to require 30-day notice with vendor reminder.
- [ ] Redlines provide exact drop-in replacement language in tracked changes.

---

## Anti-Patterns

- **Signing Vendor Paper Blindly**: Accepting standard enterprise terms without reading the limitation of liability or IP clauses.
- **Over-Redlining Minor Boilerplate**: Spending hours rewriting standard boilerplate definitions that carry zero legal risk.
- **Vague Comments**: Writing "Please revise" in the margin without providing the replacement clause text.
