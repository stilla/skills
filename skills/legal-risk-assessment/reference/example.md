# Worked Example

This example shows the expected level of specificity. Do not copy facts, scores, or mitigations unless the user's context supports them.

## Scope

* Subject: Launching a customer analytics feature that uses purchase history and behavioural events
* Jurisdictions: EU and UK
* Assessment type: Pre-decision
* Business context: Product team wants to personalise recommendations before holiday trading season

## Risk Register

* Assessment date: 2026-05-11
* Scope summary: EU and UK launch of a customer analytics feature using purchase history and behavioural events for personalised recommendations
* Assessed by: Product Legal
* Next scheduled review date: One month after launch

| ID | Category | Risk description | Severity | Likelihood | Score | Band | Strategy | Residual score | Owner | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| R1 | Data Protection | Feature may process behavioural event data for personalised recommendations without a documented lawful basis for profiling. `[AI assessment — verify with counsel]` | 4 | 3 | 12 | High | Reduce | 6 | Privacy Counsel | mitigating |
| R2 | Regulatory | EU rollout may trigger additional transparency obligations for automated decision support if the recommendations materially affect customer offers. `[AI assessment — verify with counsel]` | 3 | 3 | 9 | Medium | Reduce | 4 | Product Legal | open |
| R3 | Contractual | Vendor analytics terms may not permit use of collected events for product personalisation, creating breach risk. `[From factual context]` | 3 | 2 | 6 | Medium | Transfer | 3 | Procurement | open |

## Mitigation Plans

### R1 — Lawful basis and profiling transparency

* Action: Confirm lawful basis and update privacy notice before launch.
* Owner: Privacy Counsel
* Deadline: Before production enablement
* Residual risk: 6, assuming notice updates and opt-out handling are implemented
* Monitoring: Privacy review at launch and after first month of usage
* Approval: Senior management risk acceptance if residual score remains Medium

### R2 — Automated decision support obligations

* Action: Determine whether recommendations materially affect pricing, eligibility, or customer access to offers.
* Owner: Product Legal
* Deadline: Before EU launch decision
* Residual risk: 4, assuming recommendations remain informational and controls are documented
* Monitoring: Quarterly review of feature logic and regulatory developments
* Approval: Legal approval required before scope expansion

### R3 — Vendor analytics terms

* Action: Review vendor agreement and obtain amendment or written confirmation covering personalisation use.
* Owner: Procurement
* Deadline: Before sharing new event data with vendor
* Residual risk: 3, assuming contract confirmation is obtained
* Monitoring: Contract review on renewal
* Approval: Routine contract approval if residual score is Low
