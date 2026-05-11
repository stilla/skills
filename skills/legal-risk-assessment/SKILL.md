---
name: legal-risk-assessment
description: Identify, score, and classify legal risks using a Severity × Likelihood matrix with structured mitigation planning. Load this skill when a user asks to assess legal risk for a contract, business initiative, product feature, market entry, compliance review, or DPIA — or when they use terms like "legal exposure," "risk register," or "risk matrix." Output is always flagged for review by qualified legal professionals.
template: legal
---

# Legal Risk Assessment

> **Note:** This skill assists with legal workflows. All output must be reviewed by qualified legal professionals before being relied upon.

Load this skill when the user asks to assess legal risk for a contract, business decision, product feature, regulatory situation, or market entry.

## Progressive loading

* Load reference/categories.md during identification.
* Load reference/scoring.md before scoring.
* Load reference/example.md when the user asks for an example or when you need to model the expected register and mitigation format.

## Workflow

### Step 1 — Define scope

Before identifying risks, capture the context. Ask the user for anything missing:

| Field | What to capture |
| --- | --- |
| Subject | The thing being assessed (contract, initiative, feature, market entry) |
| Requestor | Name and department |
| Business context | What the organisation is trying to accomplish |
| Jurisdictions | Where the activity will take place or have legal effect |
| Timeline | When the activity is planned to start |
| Related matters | Existing legal issues, pending litigation, prior assessments |
| Assessment type | Pre-decision / periodic review / incident-triggered / regulatory-driven |

### Step 2 — Identify risks

Load reference/categories.md during identification. Walk through each category and assess applicability to the scoped activity.

### Step 3 — Score each risk

Before scoring, confirm the relevant jurisdictions with the user; the same risk can score very differently across EU, US, UK, and APAC contexts. Load reference/scoring.md before scoring. Use the Severity × Likelihood matrix. Never assign probability percentages — use qualitative scales only.

### Step 4 — Plan mitigation

For every risk scored Medium or above, develop a mitigation plan using one of these strategies:

| Strategy | When to use | Example |
| --- | --- | --- |
| Avoid | Eliminate the activity that creates the risk | Don't enter the market, don't process the data category, don't ship the feature |
| Reduce | Implement controls to lower severity or likelihood | Add contractual protections, implement technical safeguards, obtain regulatory clearance |
| Transfer | Shift the risk to another party | Insurance, indemnification clauses, outsource to a regulated provider |
| Accept | Proceed with full awareness | Document the decision, approval authority, and monitoring plan |

For each mitigated risk, capture:

* Specific actions with a named individual owner and deadline
* Residual risk score (re-scored after mitigation)
* Monitoring approach and frequency
* Who must approve (based on the residual risk band)
* Next scheduled review date

### Step 5 — Compile the risk register

Output the full register as a markdown table, sorted by score descending (Extreme first):

| ID | Category | Risk description | Severity | Likelihood | Score | Band | Strategy | Residual score | Owner | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| R1 | … | … | 1–5 | 1–5 | N | … | … | N | … | … |

Status must be one of: `open`, `mitigating`, `accepted`, or `closed`.

Include at the top of the register: assessment date, scope summary, assessed by, and next scheduled review date.

## Periodic review

| Type | When | Scope |
| --- | --- | --- |
| Full assessment | Annually, or when entering a new market or jurisdiction | All categories |
| Focused review | Quarterly | Extreme and High risks only |
| Triggered review | After material events (new regulation, litigation filing, incident, M&A) | Affected category |
| Post-incident | After any risk materialises | The materialised risk and related risks |

At each review: re-score existing risks, identify new risks, check mitigation progress, update the register.

## Output guidance

* Write results directly into the canvas: wrap the initial register inside a fenced markdown block when the canvas is empty, and use `str_replace` for subsequent edits. Start with scope, then the risk register table, then individual mitigation plans for Medium+ risks.
* Create change proposals for mitigation action items with named owners and deadlines.
* When assessing multiple initiatives, add a heat map table aggregating scores by category (count, average score, max score, trend vs. prior assessment). Mark trend as "Baseline" if no prior assessment exists.

## Guardrails

* Never assign probability percentages. Use the qualitative likelihood scale (Rare → Almost Certain) only.
* Never predict enforcement outcomes or litigation results — this skill scores risks, it does not predict what a regulator or court will decide.
* Out of scope: If the user asks for legal advice or a definitive answer on enforceability, decline and route to qualified counsel.
* Treat inputs and outputs as confidential. Do not echo privileged or sensitive material into public channels or third-party systems without user confirmation.
* Confirm the relevant jurisdictions before scoring any risk.
* Tag the basis for every score: `[From factual context]`, `[From regulatory framework — cite regulation and article]`, or `[AI assessment — verify with counsel]`.
* Organisation-specific risk appetite, materiality thresholds, and existing controls must come from the user — never assume them.
* Always remind the user that output must be reviewed by qualified legal professionals.