---
name: regulatory-compliance
group: Compliance
description: >-
  Map regulatory requirements to controls across fintech, healthcare and data privacy, and check
  an operation against them. Use when mapping regulatory frameworks, fintech, HIPAA, or compliance
  audits.
---

# Regulatory Compliance

Compliance risk is jurisdiction-specific and often genuinely ambiguous even to specialists — your job is to help someone structure their thinking and spot risk areas worth investigating, not to render an authoritative legal determination. Be explicit about that boundary throughout, not just in a disclaimer at the end.

## Workflow

1. **Identify the relevant domain(s) first** — advertising/marketing claims, consumer protection, industry-specific regulation (financial services, healthcare, food/beverage, etc.), employment, or general business licensing each have different regulatory bodies and standards. Ask what industry/jurisdiction if not stated, since compliance requirements are almost never universal.
2. **Separate general principles from jurisdiction-specific rules.** You can reliably explain widely-applicable concepts (e.g. "advertising claims generally need to be substantiated with evidence you actually have before making them," "material terms shouldn't be hidden in fine print") — these transfer across most jurisdictions. Specific thresholds, filing requirements, and penalty structures vary by jurisdiction and change over time; flag these as needing verification against current, jurisdiction-specific sources rather than asserting a number confidently.
3. **Build a structured risk review**, not a vague warning: for each practice/claim being reviewed, note what regulatory concern it could raise, roughly how significant that risk category tends to be, and what kind of documentation or evidence would typically mitigate it.
4. **Recommend the right kind of expert** for anything requiring a binding determination — a licensed attorney in the relevant jurisdiction, an industry-specific compliance consultant, or a regulatory filing service — rather than a generic "consult a professional" without specifying which kind actually fits the risk area identified.
5. **Help structure compliance documentation** (policies, claim-substantiation files, process checklists) when asked — this is squarely useful even without rendering legal judgment, since good documentation habits reduce risk regardless of the specific regulatory answer.

## Anti-Patterns & Constraints

- Don't state a specific regulatory threshold, filing deadline, or penalty amount as current fact without flagging that it needs verification — these change and vary by jurisdiction, and confident wrong information here is worse than an honest "verify this against the current rule."
- Don't render a determination on whether a specific practice is legal — flag the risk area and what needs expert review, rather than giving a yes/no verdict a user might rely on as if it were legal advice.
- Don't conflate this with data-privacy compliance specifically — that's a different specialized skill (`data-privacy-officer`) for GDPR/CCPA-type concerns; point there if that's what the user actually needs.

## Output format

```markdown
## Compliance review: <practice/policy being reviewed>

**Risk areas identified:**
| Area | Concern | Rough risk level | What would help |

**Needs expert verification:** [specific items requiring a licensed professional or current regulatory source, and which kind of expert fits]

**Documentation suggestions:** [if applicable]
```

## Verification & Quality Checklist

- [ ] Jurisdiction and effective date stated for every rule or threshold cited.
- [ ] Governing authority or regulation named, not paraphrased generically.
- [ ] Scope-of-advice boundary stated explicitly in the output.
- [ ] A named human review step identified before anything is acted on.

## References

Load these only when the task needs them:

- [references/iso-27001.md](references/iso-27001.md)
