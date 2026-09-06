---
name: contract-drafting
group: Contracts
description: >-
  Draft the agreements a small company signs: NDA, MSA, SOW, contractor and consulting terms. Use
  when drafting NDAs, MSAs, Statements of Work, or consulting agreements.
---

# contract-drafting

## Core Philosophy
Contract drafting is not padding 30 pages of boilerplate legalese to sound impressive or intimidate counterparties. Ambiguous, overwrought contracts create costly litigation and destroy commercial deals. Exceptional contract drafting is architectural engineering in plain language: establishing clear scope boundaries, defining unambiguous deliverables and acceptance criteria, balancing commercial liability, and eliminating interpretive friction.

---

## 4-Step Commercial Contract Drafting Framework

### Step 1: Modular Contract Architecture (MSA + SOW)
1. **The Two-Tier Architecture**:
   - *Master Services Agreement (MSA)*: Governs the permanent legal relationship: confidentiality, intellectual property ownership, indemnification, limitation of liability, governing law, and dispute resolution.
   - *Statement of Work (SOW)*: Governs the specific commercial project: exact technical deliverables, milestones, acceptance criteria, timeline, pricing, and payment schedules.
2. **Order of Precedence Clause**:
   - Always state which document controls in the event of a conflict (standard: SOW controls technical scope and pricing; MSA controls legal liabilities and IP terms).

### Step 2: Deliverables, Milestones & Acceptance Criteria
1. **Objective Acceptance Testing Protocol**:
   - Never use subjective phrases like "to client's complete satisfaction".
   - Structure a deterministic acceptance window:
     - Client has strictly **10 business days** from delivery to test deliverables against agreed technical specifications.
     - Rejection requires written, detailed defect notices identifying specific spec failures.
     - Deemed Acceptance: If client fails to provide written rejection within 10 business days, deliverables are legally deemed accepted.

### Step 3: Intellectual Property (IP) Ownership & Licensing
1. **Work Made for Hire vs Pre-Existing IP**:
   - *Custom Deliverables*: Assigned to client upon **full receipt of payment** (never before payment clears).
   - *Pre-Existing Contractor Materials / Tools*: Retained by developer. Client receives a perpetual, non-exclusive, royalty-free license to use the tools solely as integrated into the final deliverable.

### Step 4: Risk Allocation & Commercial Guardrails
1. **Limitation of Liability (LoL) Architecture**:
   - Mutual aggregate liability cap strictly limited to **fees paid by client in the preceding 12 months**.
   - Express exclusion of indirect, consequential, punitive, or special damages (loss of profits, lost data).
2. **Scope Creep & Change Order Mechanics**:
   - Any work beyond the explicit SOW requires a signed written Change Order specifying additional fee schedule and timeline adjustments.

---

## Deliverable Format: Professional Statement of Work (`SOW-TEMPLATE.md`)

```markdown
# Statement of Work #01: [Project Name]
This Statement of Work ("SOW") is entered into under the Master Services Agreement dated [Date] between [Provider Name] ("Provider") and [Client Name] ("Client").

## 1. Project Scope & Technical Deliverables
- **Deliverable 1.1**: Production-ready REST API implemented in Go matching OpenAPI spec v1.2.
- **Deliverable 1.2**: Automated test suite achieving >= 80% test coverage.
- **Deliverable 1.3**: Deployment automation scripts using Terraform on AWS ECS.

## 2. Explicit Out-of-Scope Items
- Frontend UI development or mobile application wrappers.
- Database migration of legacy data prior to 2024.

## 3. Milestones & Payment Schedule
| Milestone # | Description | Target Delivery Date | Fee ($ USD) |
|---|---|---|---|
| M-01 | Architecture Design & Schema Spec | [YYYY-MM-DD] | $10,000 (Due upon signing) |
| M-02 | Core API Implementation & Tests | [YYYY-MM-DD] | $15,000 (Due upon delivery) |
| M-03 | Production Deployment & Sign-off | [YYYY-MM-DD] | $10,000 (Due upon acceptance) |

## 4. Acceptance Procedure
Client shall have ten (10) business days following delivery to verify Deliverables against specifications. In the absence of written notice specifying non-conformities within such period, Deliverables shall be deemed conclusively accepted.
```

---

## Worked Example: High-Stakes API Engineering SOW

- **Context**: Consulting firm drafted an SOW for a $60k billing engine integration.
- **Key Clause**: Included the 10-day "Deemed Acceptance" clause and conditioned IP transfer upon final payment receipt.
- **Payoff**: Client stalled final payment for 60 days claiming minor scope additions. The provider pointed to the Deemed Acceptance clause and withheld IP assignment; client paid invoice in full within 48 hours.

---

## Verification Checklist

- [ ] Contract is partitioned into a legal MSA and technical/commercial SOW.
- [ ] Deliverables include objective, verifiable acceptance testing criteria.
- [ ] Deemed acceptance window (e.g. 10 business days) is explicitly defined.
- [ ] Intellectual property assignment is conditioned upon full payment receipt.
- [ ] Aggregate liability is capped at fees paid in preceding 12 months with consequential damages waived.

---

## Anti-Patterns

- **Subjective Acceptance**: Agreeing that payment depends on "client's subjective aesthetic approval".
- **Uncapped Liability**: Signing contracts with unlimited liability for standard software bugs.
- **IP Assignment Before Payment**: Transferring complete copyright ownership to the client before the invoice has been paid.
