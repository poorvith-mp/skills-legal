---
name: ip-protection
group: Intellectual property
description: >-
  Protect the work: trademark strategy, copyright, trade secrets and IP assignment clauses that
  actually hold. Use when protecting trademarks, copyrights, trade secrets, or IP assignment.
---

# ip-protection

## Core Philosophy
In technology and software companies, Intellectual Property (IP) is frequently the primary asset driving enterprise value. IP protection is not simply filing an expensive patent that gathers dust. A comprehensive IP strategy orchestrates the four distinct pillars of intellectual property: Patents (novel algorithms/inventions), Trademarks (brand goodwill and search dominance), Copyrights (source code and visual assets), and Trade Secrets (confidential proprietary algorithms). Leaving IP assignment unexecuted or trade secrets unmanaged destroys investment value.

---

## 4-Step Comprehensive IP Protection Architecture

### Step 1: The 4 Pillars of Intellectual Property
1. **Patents (Utility & Design)**:
   - Protect novel, non-obvious, and useful processes, machines, or technical architectures.
   - *Timing*: Must file a Provisional Patent Application **prior to any public disclosure, blog post, or open-source release** (US has a 1-year grace period; most international jurisdictions require absolute novelty).
2. **Trademarks (Brand Identity)**:
   - Protect brand names, logos, and slogans on the USPTO Principal Register.
   - Enforce distinctiveness: Fanciful (e.g. *Spotify*, *Xerox*) or Arbitrary (e.g. *Apple*) marks receive highest legal protection; descriptive marks (e.g. *Fast Cloud Database*) are weak or unregistrable.
3. **Copyrights (Source Code & Creative Works)**:
   - Protect original works of authorship fixed in a tangible medium.
   - Automatic upon creation, but formal US Copyright Office registration is required before bringing an infringement lawsuit or claiming statutory damages ($150,000 per willful infringement).
4. **Trade Secrets (Defend Trade Secrets Act - DTSA)**:
   - Protect confidential business information deriving independent economic value from being secret (e.g. proprietary ranking algorithms, internal benchmark datasets, customer pricing models).

### Step 2: Unbroken Chain of Title & IP Assignment
1. **The Universal Assignment Mandate**:
   - Every founder, employee, advisor, and external contractor must sign a comprehensive Invention Assignment Agreement *before* writing their first line of code.
   - For contractors: Must include explicit **"Work Made for Hire"** language **AND** an express present assignment of future inventions (*"Contractor hereby irrevocably assigns to Company all right, title, and interest..."*).

### Step 3: Trade Secret Governance & Reasonable Measures
1. **The Statutory "Reasonable Measures" Standard**:
   - Under the DTSA and UTSA, trade secret protection is legally forfeited if the owner fails to take reasonable measures to maintain secrecy:
     - Access Control: Role-based access control (RBAC) and least-privilege repository permissions.
     - Non-Disclosure Agreements (NDAs): Required prior to sharing proprietary tech with partners or prospective investors.
     - Code Obfuscation & Security: Private GitHub repositories, end-to-end encryption of sensitive datasets, and watermarked internal documents.

### Step 4: Open-Source Ingestion & Contamination Defense
1. **Inbound OSS License Auditing**:
   - Implement automated license compliance scanning (`fossa`, `snyk`, `license-checker`) in CI pipelines.
   - Ban strong copyleft licenses (GPL v2/v3, AGPL v3) from proprietary commercial codebases to prevent viral licensing contamination.

---

## Deliverable Format: Intellectual Property Portfolio Register (`IP-PORTFOLIO.md`)

```markdown
# Intellectual Property Portfolio & Strategy: [Company Name]

## 1. Trademark Registry
| Mark / Brand | Classes | Jurisdiction | Serial / Reg # | Status | Renewal Due |
|---|---|---|---|---|---|
| [Brand Name] | Class 9 (Software), Class 42 (SaaS) | USPTO | 98/123,456 | Registered | 2030-05-12 |
| [Logo Asset] | Class 42 | EUIPO | 018234567 | Under Examination | - |

## 2. Patent Strategy & Filings
- **Patent 1**: *Method and System for Zero-Downtime Distributed Database Schema Migration*
  - Type: US Provisional Patent Application
  - Application #: [63/XXX,XXX] | Filing Date: [YYYY-MM-DD]
  - Priority Deadline (to file Non-Provisional): [YYYY-MM-DD (12 months out)]

## 3. Trade Secret Inventory & Protection Controls
| Asset ID | Trade Secret Asset | Economic Value | Reasonable Security Measures Enforced |
|---|---|---|---|
| TS-01 | Proprietary Vector Re-ranking Algorithm | Core competitive latency advantage | Stored in private monorepo; accessible only by Core ML team |
| TS-02 | Enterprise Customer Churn Predictor | Increases gross retention by 4% | Database encrypted at rest; KMS key access logged |

## 4. IP Assignment Chain of Title Audit
- [x] 100% of current and former employees have signed CIIAA.
- [x] 100% of third-party contractor SOWs include present IP assignment clauses.
- [x] Zero AGPL/GPL copyleft dependencies present in commercial build artifact.
```

---

## Worked Example: Pre-Funding Trademark Clearance

- **Context**: A startup named their database product "NexusDB" and operated for 6 months.
- **Audit**: Comprehensive USPTO trademark search revealed an existing enterprise hardware company owned "Nexus" for data storage software (Class 9).
- **Remediation**: Rebranded to an arbitrary coined name ("Qdrant-style") before commercial launch and registered the new mark.
- **Outcome**: Avoided an immediate trademark cease-and-desist letter and expensive post-Series-A rebrand.

---

## Verification Checklist

- [ ] Every founder, employee, and contractor has executed a signed Invention Assignment Agreement.
- [ ] Trademark clearance searches verify availability before launching products or public brand names.
- [ ] Provisional patent applications are filed prior to any public talk, blog post, or open-source release.
- [ ] Trade secrets are documented and protected by strict technical access controls and NDAs.
- [ ] CI pipeline scans third-party dependencies to block copyleft contamination (AGPL).

---

## Anti-Patterns

- **Publishing Before Filing**: Publishing an academic whitepaper or blog post detailing an algorithm before filing a provisional patent.
- **Missing Contractor Assignments**: Paying a $50,000 contractor fee without a written contract, leaving the contractor as the legal copyright owner of the code.
- **Assuming Trademarks are Automatic**: Thinking that registering a `.com` domain gives you legal trademark rights.
