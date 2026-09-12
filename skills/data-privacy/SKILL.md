---
name: data-privacy
last_reviewed: 2026-09-06
group: Product and website
description: >-
  Run the privacy programme: data mapping, lawful basis, DSAR handling, retention schedules and
  breach response. Use when managing GDPR/CCPA compliance, DSAR requests, or data mapping.
---

# data-privacy

## Core Philosophy
Data privacy compliance (GDPR in Europe, CCPA/CPRA in California, LGPD in Brazil) is not a static legal disclaimer copy-pasted into a website footer. Privacy is an engineering architecture. Modern regulations enforce strict principles: privacy by design, data minimization, lawful basis justification, automated Data Subject Access Request (DSAR) fulfillment within 30 days, and mandatory 72-hour breach reporting. Violating data privacy carries statutory fines reaching 4% of global annual turnover or $20M under GDPR.

---

## 4-Step Technical Data Privacy Architecture

### Step 1: Data Inventory & Record of Processing Activities (ROPA / Art. 30)
1. **The Comprehensive Data Flow Map**:
   - Track every personal data element across its lifecycle (Collection -> Storage -> Processing -> Sharing -> Destruction).
   - Document: Data categories (PII, IP address, financial, sensitive data), Data Subjects (customers, employees), Storage location (AWS us-east-1), Retention period, Subprocessors (Stripe, PostHog, AWS).
2. **Lawful Basis for Processing (GDPR Art. 6)**:
   - Identify lawful basis for every processing stream: *Contractual Necessity*, *Legal Obligation*, *Legitimate Interest* (with documented Legitimate Interest Assessment - LIA), or *Explicit Consent*.

### Step 2: Consent Management & Cookie Governance (ePrivacy)
1. **Prior Consent Mandate in the EU**:
   - Tracking, analytics, and marketing cookies must **never** be fired prior to affirmative, opt-in consent from the user.
   - Pre-ticked checkboxes and cookie walls (blocking access unless consent is given) are legally invalid under EDPB guidelines.
2. **Granular Consent Categories**:
   - Strictly Necessary (Always active).
   - Analytics / Performance (Opt-in required).
   - Advertising / Marketing (Opt-in required).

### Step 3: Automated Data Subject Access Request (DSAR) Pipeline
1. **Statutory Rights Fulfillment (Within 30 Calendar Days)**:
   - *Right to Access / Portability*: Provide user all stored personal data in a structured, machine-readable format (JSON/CSV).
   - *Right to Erasure ("Right to Be Forgotten")*: Delete user PII across primary databases, logs, backups, and subprocessor systems.
2. **The "Hard Delete" Engineering Protocol**:
   - Execute cryptographic erasure or anonymization of relational database records (`user_id -> hash`).
   - Retain strictly what is legally required for financial/tax audits (e.g. 7-year invoice records) with PII redacted.

### Step 4: Subprocessor Management & 72-Hour Breach Response
1. **Data Processing Agreements (DPAs) & Cross-Border Transfers**:
   - Execute signed DPAs with all third-party vendors containing EU Standard Contractual Clauses (SCCs) and UK Addendums.
2. **The 72-Hour Incident Response Protocol**:
   - If a personal data breach occurs, notify the Lead Supervisory Authority (DPA) within **72 hours** of becoming aware of the breach under GDPR Art. 33.
   - If high risk to individuals: Notify impacted data subjects without undue delay.

---

## Deliverable Format: Data Privacy Architecture & ROPA Spec (`PRIVACY-SPEC.md`)

```markdown
# Data Privacy Architecture & ROPA Register: [Product Name]

## 1. Record of Processing Activities (ROPA - GDPR Art. 30)
| Processing Activity | Personal Data Categories | Data Subjects | Lawful Basis | Storage Location | Retention Limit |
|---|---|---|---|---|---|
| User Authentication | Email, Hashed Password, IP | Registered Users | Contractual Necessity | Postgres (AWS Dublin) | Account Life + 30 Days |
| Payment Processing | Billing Address, Last 4 Card | Paying Customers | Legal Obligation / Contract | Stripe Inc. (US) | 7 Years (Tax law) |
| Product Analytics | Anonymized User ID, Click events | Web Visitors | Consent (Opt-in) | PostHog (EU Cloud) | 12 Months |

## 2. Subprocessor Roster & Transfer Mechanisms
- **Stripe, Inc.**: Payments infrastructure | DPA + EU Standard Contractual Clauses (SCCs)
- **Amazon Web Services (AWS EMEA)**: Cloud hosting | DPA + ISO 27001 certified

## 3. DSAR Automated Erasure Protocol (`DELETE /api/v1/user/dsar`)
1. Invalidate active user session and auth tokens.
2. Scramble PII in `users` table: `email = anonymized_${uuid}@deleted.local`.
3. Dispatch webhook to Stripe and PostHog to trigger downstream deletion.
4. Return 200 OK with confirmation receipt to data subject.

## 4. 72-Hour Breach Notification Escalation
- Lead DPA: Irish Data Protection Commission (DPC)
- Escalation Team: General Counsel, CISO, CTO
- Emergency Notification Template: `legal/templates/breach-notification-dpa.md`
```

---

## Worked Example: Automated Right to Be Forgotten Pipeline

- **Challenge**: User invoked GDPR Art. 17 erasure request. Engineering faced manual deletion across 8 databases and 4 third-party SaaS tools.
- **Solution**: Built an automated asynchronous DSAR worker in AWS Lambda. On verified request, the worker cascaded soft-deletes into hard cryptographic anonymization and sent automated erasure webhooks to Stripe and Segment.
- **Outcome**: DSAR turnaround time dropped from 14 days of manual engineering to 90 seconds automated; full compliance audit trail generated.

---

## Verification Checklist

- [ ] Record of Processing Activities (ROPA) documents all personal data flows and lawful bases.
- [ ] Cookie consent banners require affirmative opt-in before firing analytics or ad trackers in the EU.
- [ ] Automated DSAR export and erasure endpoints function and fulfill requests within 30 days.
- [ ] Signed Data Processing Agreements (DPAs) with SCCs are executed for all third-party subprocessors.
- [ ] 72-hour statutory breach reporting procedure is documented and tested with leadership.

---

## Anti-Patterns

- **Pre-Ticked Cookie Banners**: Assuming implied consent or using deceptive dark patterns that violate EDPB rulings.
- **Ignoring Subprocessor Deletion**: Deleting the user from your local database while leaving their raw PII in your CRM and analytics tools.
- **Hiding Breach Incidents**: Waiting 3 months to notify regulators of a data leak, triggering maximum statutory penalties.
