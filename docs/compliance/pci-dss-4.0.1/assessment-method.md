# PCI DSS v4.0.1 Banking Assessment Method

## 1. Assessment objective

Determine, for a defined period and boundary, whether each applicable PCI DSS requirement is implemented and operating effectively, whether evidence is sufficient, and whether the conclusion can be reproduced by an independent reviewer.

This pack supports a readiness assessment or internal control assessment. A formal ROC, SAQ, AOC, or assessor report must follow the current PCI SSC reporting instructions and the engagement scope agreed with the qualified assessor.

## 2. Governance and independence

| Role | Accountability |
|---|---|
| Executive sponsor | Removes blockers, accepts enterprise residual risk, and receives the conclusion. |
| PCI programme owner | Owns scope, plan, evidence quality, issue governance, and assessor coordination. |
| CDE/system owners | Implement controls and provide complete evidence. |
| First-line control operators | Perform controls and retain operational records. |
| Second-line risk/compliance | Challenges scope, design, evidence, risk analysis, and closure. |
| Internal audit or independent reviewer | Provides independent assurance where included in the plan. |
| QSA/ISA liaison | Ensures official validation and reporting expectations are understood. |
| Third-party owners | Obtain provider responsibilities, AOCs/ROCs where relevant, and manage dependencies. |

The person who operates a control should not be the sole person deciding whether evidence proves that control.

## 3. Phase 0 — Define the assessment boundary

Do not accept a CDE diagram as scope proof. Perform discovery using:

- Card-data-flow interviews with issuing, acquiring, merchant-services, ATM, branch, call-centre, digital, fraud, and settlement teams.
- Network, cloud, identity, endpoint, database, application, logging, vulnerability, and vendor inventories.
- PAN discovery or data-flow validation using approved, controlled methods.
- Review of backups, replicas, DR, analytics, tickets, email, logs, recordings, test data, and removable media.
- Payment brand, acquirer, processor, gateway, and contractual obligations.

Classify every component as **in CDE**, **connected-to**, **security-impacting**, **service provider**, or **out of scope with evidence**. Record the rationale and test the isolation claim. Scope must include people and processes, not only IP ranges.

### Boundary exit criteria

- Approved CDE and data-flow diagrams dated for the assessment.
- Complete component and service inventory with owners and environment.
- List of CHD/SAD stores, flows, transformations, and deletion points.
- Documented segmentation controls and validation results.
- DR, backup, branch, ATM, cloud, remote-support, and provider paths addressed.
- Scope assumptions, exclusions, and unresolved unknowns logged and escalated.

## 4. Phase 1 — Plan and request evidence

Create an evidence request with requirement, control objective, population, period, owner, due date, format, and quality criteria. Request raw exports and system records wherever possible.

Use a dated evidence cut-off. Evidence produced after the cut-off may demonstrate remediation but must not silently rewrite the assessed period.

## 5. Phase 2 — Test design and sampling

Use the official PCI DSS testing procedures as the anchor. Supplement them with:

- **Inquiry:** interview the control operator and owner; corroborate answers.
- **Observation:** watch the control being performed or inspect physical operation.
- **Inspection:** inspect policies, configurations, tickets, reports, records, and logs.
- **Reperformance:** independently repeat a calculation, query, configuration check, or sample selection.
- **Technical validation:** scan, test segmentation, inspect traffic, validate logging, or review code where authorised.

Define the population before selecting a sample. Document the period, selection method, sample size rationale, replacements, exceptions, and conclusions. A sample is not evidence that an untested population is complete; population completeness is itself a test.

### Suggested internal readiness sample policy

This policy is a starting point, not a PCI SSC-prescribed sample size:

| Population | Starting approach |
|---|---|
| Fewer than 10 items | Test all, unless the assessor directs otherwise. |
| 10–100 items | Risk-based sample across systems, owners, locations, and periods; document rationale. |
| More than 100 items | Stratify by risk and technology, then sample each material stratum; increase for exceptions or failures. |
| Monthly/quarterly recurring control | Select multiple periods, including the oldest, newest, and a high-change period. |
| Critical provider or unique system | Test the unique item; do not hide it in a broad sample. |

## 6. Phase 3 — Rate each requirement

Use these internal statuses:

| Status | Meaning |
|---|---|
| Compliant | Applicable control is implemented, operating, and supported by sufficient evidence for the assessed period. |
| Partially compliant | Some control elements or population segments pass, but a material gap remains. |
| Non-compliant | The applicable requirement is not implemented or the control failed materially. |
| Not applicable | Documented analysis demonstrates the requirement does not apply to the assessed scope; approval is required. |
| Compensating control | A formally documented alternative is used where allowed, with required rationale and validation. |
| Not assessed | Work was not performed; this is not a compliant conclusion. |
| Unknown | Scope, population, or evidence is insufficient to make a conclusion. Escalate immediately. |

Never convert missing evidence into “compliant.” Record the limitation and its impact.

## 7. Phase 4 — Issue severity and remediation

Rate internal issues using impact, exploitability, scope, duration, data sensitivity, regulatory or contractual consequence, and control detectability. A critical issue affecting PAN exposure, SAD retention, segmentation failure, privileged access, or inability to detect activity requires immediate escalation.

Every issue must contain:

- Requirement and testing procedure.
- Condition and reproducible evidence.
- Affected population and assessment period.
- Risk and likely consequence.
- Root cause, not only symptom.
- Accountable executive and operational owner.
- Immediate containment or compensating control.
- Sustainable action, milestone, due date, and dependency.
- Closure evidence and independent validation method.
- Risk acceptance authority, expiry, and monitoring where applicable.

## 8. Phase 5 — Report and challenge

The report should include:

1. Executive conclusion and scope limitations.
2. CDE and data-flow summary.
3. Coverage by requirement and status.
4. Top risks and immediate actions.
5. Evidence limitations and unknowns.
6. Third-party dependency and responsibility matrix.
7. Detailed findings and management responses.
8. Remediation roadmap and decision requests.
9. Change log and approvals.

Before release, perform a quality review: trace every conclusion to evidence, confirm no evidence belongs to another period or environment, test all “not applicable” claims, and reconcile the issue register to the executive summary.

## 9. Banking assessment programme

| Week | Focus | Exit evidence |
|---:|---|---|
| 1 | Governance, scope, and data-flow discovery | Approved scope plan, stakeholder map, assumptions log |
| 2 | Network, cloud, identity, and provider inventory | CDE diagrams, component inventory, provider register |
| 3 | Requirements 1–4 | Network, configuration, storage, and transmission test results |
| 4 | Requirements 5–6 | Malware, vulnerability, SDLC, change, and web-application evidence |
| 5 | Requirements 7–8 | Access, MFA, privileged access, and lifecycle testing |
| 6 | Requirements 9–10 | Physical and logging coverage/testing results |
| 7 | Requirements 11–12 | Security testing, governance, incident, awareness, and TPSP results |
| 8 | Challenge and reporting | Draft findings, management responses, executive pack |
| 9–12 | Remediation validation | Retest results, residual-risk decisions, readiness conclusion |
