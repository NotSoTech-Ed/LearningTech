# SOC 2 Type II Assessment Method

## 1. Assessment objective

Prepare evidence and conclusions showing that controls within the defined system were suitably designed and operated effectively throughout the specified Type II period for the selected Trust Services Criteria.

## 2. Governance

| Role | Accountability |
|---|---|
| Executive sponsor | Owns customer trust, resources, risk decisions, and report response. |
| SOC programme owner | Coordinates system description, controls, evidence, auditor requests, and exceptions. |
| Control owner | Operates the control consistently and retains evidence. |
| System owner | Maintains accurate system boundaries, data flows, dependencies, and changes. |
| Legal/privacy/compliance | Validates commitments, regulatory obligations, privacy disclosures, and responses. |
| Customer success / sales | Ensures external commitments match the assessed system and report. |
| Internal assurance | Challenges design, evidence, scope, and remediation independently. |
| Service auditor | Performs the examination and issues the SOC 2 report. |

## 3. Phase 1 — System and criteria scoping

Prepare a scope memo with:

- Legal entity, services, products, customers, locations, and period.
- System boundary and components.
- Selected TSC categories and control objectives.
- Customer commitments and applicable laws.
- Subservice organisations and carve-out/inclusive method.
- Complementary user entity controls.
- Significant changes, incidents, outages, and exclusions.

Challenge the boundary against contracts, architecture, production inventories, support processes, cloud accounts, endpoints, disaster recovery, and third-party data flows.

## 4. Phase 2 — Risk and control design

For each criterion or control objective:

1. Identify the threat or failure condition.
2. State the control activity and owner.
3. Define frequency, population, evidence, and exception handling.
4. Map dependencies and complementary controls.
5. Confirm the control operated throughout the period or record its effective date.
6. Define the test that would prove operation.

Assess design for precision. “Management reviews security” is not precise enough without a defined population, review criteria, evidence, frequency, and response to exceptions.

## 5. Phase 3 — Evidence and operating testing

Use inquiry, inspection, observation, reperformance, and technical validation. For each control, establish:

- Complete population and source.
- Sample selection and period coverage.
- Performer and reviewer identity.
- Evidence timestamp and system provenance.
- Exceptions and correction.
- Whether the control operated consistently.

For automated controls, test configuration, change management, inputs, outputs, monitoring, and failure alerts. For availability controls, test SLO measurement, incident handling, capacity, backup, recovery, and customer communication.

## 6. Phase 4 — Exception evaluation

Evaluate frequency, duration, magnitude, cause, affected customers, data, commitments, and compensating controls. A single exception may be significant if it affects a critical control or sensitive customer data. Multiple small exceptions may indicate a systemic issue.

Determine whether an exception requires:

- Corrective action during the period.
- Modification to the system description.
- Disclosure in the report's tests and results.
- Customer or regulator notification.
- Contract or commitment review.
- Expansion of testing.

## 7. Phase 5 — Report readiness and quality review

Before the service auditor begins final work:

1. Reconcile the system description to production reality.
2. Validate every criterion has an owner and evidence.
3. Review evidence for period coverage and completeness.
4. Log all exceptions before the auditor discovers them.
5. Validate subservice and complementary controls.
6. Confirm incidents and significant changes are accurately disclosed.
7. Prepare management responses without minimising exceptions.
8. Run an independent quality review and retain the audit trail.

## 8. Type II operating calendar

| Period | Activity | Output |
|---|---|---|
| Pre-period | Scope, criteria, system description, risk assessment, control design | Approved readiness baseline |
| Month 1 | Auditor planning and population definition | PBC list and sample approach |
| Monthly/quarterly | Operate controls, review evidence, remediate exceptions | Dated evidence and issue updates |
| Mid-period | Interim readiness review and change impact assessment | Exception trend and corrective actions |
| Period end | Final evidence, incidents, changes, and management assertion | Complete period evidence package |
| Reporting | Auditor testing, management responses, report review | Final SOC 2 Type II report |

## 9. Banking-specific assessment focus

Prioritise payment and transaction processing integrity, customer and privileged access, encryption and key management, cloud resilience, RTO/RPO evidence, fraud and anomaly monitoring, customer data segregation, API security, incident notification commitments, provider dependencies, and regulatory audit trails.
