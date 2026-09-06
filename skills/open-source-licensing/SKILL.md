---
name: open-source-licensing
group: Intellectual property
description: >-
  Choose a licence, comply with the ones you depend on, and resolve copyleft conflicts before they
  ship. Use when choosing OSS licenses, resolving copyleft, or dependency compliance.
---

# open-source-licensing

## Core Philosophy
Open-source software (OSS) powers the modern software ecosystem, but using or releasing open-source code without license discipline is a severe legal trap. Open-source licenses are legally binding copyright licenses. Violating copyleft licenses (such as GPL or AGPL) can force a company to legally disclose proprietary commercial source code to the public. Professional engineering organizations maintain strict license taxonomy awareness, automated CI compliance scanners, and clear outbound licensing strategies.

---

## 4-Step Open Source License Architecture

### Step 1: The Open Source License Taxonomy
1. **Permissive Licenses (Commercial-Friendly)**:
   - *MIT*: Minimalist. Allows reuse, modification, and commercialization with attribution and copyright notice retention.
   - *Apache 2.0*: Permissive with an **explicit patent grant** and patent retaliation clause (terminating license if recipient sues for patent infringement). Preferred standard for modern tech tools.
   - *BSD (2-Clause / 3-Clause)*: Similar to MIT; BSD 3-Clause prohibits using contributors' names for endorsement.
2. **Weak / File-Level Copyleft**:
   - *Mozilla Public License (MPL 2.0) & LGPL*: Modifications to the licensed file itself must remain open-source, but larger software products linking to the library may remain proprietary.
3. **Strong / Network Copyleft (The Viral Hazard)**:
   - *GPL v2 / GPL v3*: Any derivative work distributed to third parties must be licensed under GPL and disclose full source code.
   - *Affero GPL (AGPL v3)*: Closes the "SaaS loophole". Triggered by **network access** (running on a server accessed over the internet), compelling full source code disclosure. Banned in most commercial SaaS proprietary backends.

### Step 2: The Modern Fair-Source & Source-Available Movement
1. **Post-Open Source Licenses for Infrastructure Tools**:
   - When defending against hyperscaler cloud exploitation (e.g. AWS selling your open-source tool as a managed service without contributing back):
     - *Business Source License (BSL 1.1 / BUSL)*: Free for development and internal use; commercial managed-service monetization requires license. Automatically converts to Apache/GPL after 4 years.
     - *Server Side Public License (SSPL)*: MongoDB's license requiring anyone offering the software as a service to open-source their entire supporting infrastructure stack.

### Step 3: Shift-Left Dependency License Scanning in CI
1. **Automated License Gating**:
   - Integrate automated license scanning into GitHub Actions / CI (`license-checker`, `cargo-deny`, `fossa`, `snyk`).
   - Define strict policy:
     - **ALLOW**: MIT, Apache-2.0, BSD-2-Clause, BSD-3-Clause, ISC, CC0.
     - **REVIEW**: MPL-2.0, LGPL-3.0.
     - **FAIL / BLOCK**: GPL-2.0, GPL-3.0, AGPL-3.0, SSPL, Commons Clause.

### Step 4: Software Bill of Materials (SBOM) Generation
1. **Compliance Documentation**:
   - Generate automated SBOMs matching **SPDX** or **CycloneDX** specifications on every release.
   - Package third-party notices (`THIRD_PARTY_LICENSES.txt`) bundled into binary releases to satisfy legal attribution obligations.

---

## Deliverable Format: OSS License Compliance Specification (`OSS-LICENSE-SPEC.md`)

```markdown
# Open Source License Governance Specification: [Project / Org Name]

## 1. Outbound Project License
- **License Selected**: **Apache License 2.0**
- **Rationale**: Permissive commercial adoption with explicit contributor patent grant protection.
- **License Header**: Standard Apache 2.0 SPDX identifier on all source files:
  `// SPDX-License-Identifier: Apache-2.0`

## 2. Inbound Dependency Policy Matrix
| License Category | Approved Licenses | Usage Permitted | CI Enforcement Action |
|---|---|---|---|
| Permissive | MIT, Apache-2.0, BSD-3-Clause, ISC | Yes (Any context) | Pass |
| Weak Copyleft | MPL-2.0, LGPL-2.1/3.0 | Review (Dynamic link only) | Manual Review Required |
| Strong Copyleft | GPL-2.0, GPL-3.0, AGPL-3.0 | **PROHIBITED** in backend | **FAIL BUILD** |

## 3. Automated CI Scanner Configuration (`.cargo-deny.toml` / `license-checker`)
```toml
[licenses]
allow = [
    "MIT",
    "Apache-2.0",
    "BSD-3-Clause",
    "ISC"
]
deny = [
    "AGPL-3.0",
    "GPL-3.0",
    "SSPL-1.0"
]
```

## 4. Third-Party Attribution Manifest
- Generated via `cargo-bundle-licenses` / `npx license-checker --csv > THIRD_PARTY_NOTICES.csv` on release.
```

---

## Worked Example: Blocking an AGPL Dependency in a SaaS Ingestion Worker

- **Incident**: A developer imported an AGPL-3.0 Go library for PDF parsing into a proprietary cloud billing worker.
- **Detection**: CI pipeline failed PR checks: `cargo-deny / license-checker flagged AGPL-3.0 license violation on github.com/vendor/pdf-engine`.
- **Remediation**: Replaced library with an Apache-2.0 alternative before code landed in `main`.
- **Outcome**: Prevented viral copyleft contamination of the proprietary billing codebase.

---

## Verification Checklist

- [ ] Project repository contains a clean, root-level `LICENSE` file.
- [ ] Source files include SPDX license identifiers in top comments.
- [ ] Inbound CI scanner blocks GPL/AGPL dependencies from commercial proprietary code.
- [ ] Automated SBOM (SPDX or CycloneDX) generated during release builds.
- [ ] Third-party license attribution notices are bundled with distributed binary artifacts.

---

## Anti-Patterns

- **Accidental AGPL Ingestion**: Merging an AGPL-licensed package into a SaaS backend, exposing the proprietary repo to source code disclosure demands.
- **No License File**: Publishing open-source code on GitHub without a `LICENSE` file (by default, copyright is fully reserved; legally nobody can use it).
- **Stripping Copyright Notices**: Deleting third-party MIT or BSD copyright headers when copying utility code.
