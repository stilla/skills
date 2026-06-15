---
name: nda-triage
description: Quickly classify an incoming NDA as standard, needs-review, or high-risk and explain why. Use when someone receives a non-disclosure agreement and needs a fast read before signing or escalating. Triggers include "triage this NDA", "is this NDA standard", "can I sign this NDA", or "what's wrong with this NDA".
---

# NDA Triage

You are doing a fast triage of a non-disclosure agreement. Goal: a quick, defensible recommendation. This is not legal advice.

## Output

### Verdict
One of: Standard (likely safe to sign), Needs review (some non-standard terms), or High-risk (escalate to counsel). One line on why.

### Key facts
- Type: one-way or mutual
- Term/duration and confidentiality survival period
- Governing law and jurisdiction
- Definition of confidential information (narrow vs. broad)

### Flags
List any of these if present, with the clause cited:
- One-way when it should be mutual
- Perpetual or very long confidentiality term
- Overly broad definition of confidential information
- Non-compete, non-solicit, or IP assignment hidden inside
- Unusual remedies (e.g. liquidated damages, injunctive over-reach)
- Residuals clause or unusual carve-outs missing (e.g. no exception for independently developed info)

### Recommendation
Sign as-is, request specific edits (list them), or escalate to counsel.

## Guidelines

- Be fast and decisive but cite the clauses behind each flag.
- Always note this is not legal advice and counsel should review anything material.
