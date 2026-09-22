# SOC 2 Type II Knowledge Base

## 1. What a Type II examination covers

A SOC 2 report evaluates controls at a service organisation relevant to one or more Trust Services Criteria (TSC). Type I addresses design at a point in time. **Type II** addresses design and operating effectiveness over a specified period.

The report has a system description, management assertion, auditor opinion, control objectives or criteria, control activities, tests of controls, results, exceptions, and other information such as complementary user entity controls or subservice organisations.

## 2. Trust Services Criteria

| Category | Control objective in a banking service |
|---|---|
| Security | Protect the system against unauthorised access, use, or modification. This is the common criteria category and the baseline for most engagements. |
| Availability | Operate and maintain the system to meet availability commitments and objectives. |
| Processing integrity | Process transactions completely, accurately, timely, and authorised according to commitments. |
| Confidentiality | Protect confidential information according to commitments and system requirements. |
| Privacy | Collect, use, retain, disclose, and dispose of personal information in accordance with commitments and applicable privacy requirements. |

Select categories based on customer commitments, contracts, regulation, service risk, and user needs. Do not claim a category is covered merely because a related policy exists.

## 3. System description boundary

Describe the services and system in enough detail for a user to understand:

- Services and products, including payment, identity, lending, data, API, or managed security services.
- Infrastructure, applications, databases, networks, endpoints, facilities, and cloud regions.
- Data flows, information classification, customer tenancy, encryption, key management, and deletion.
- People, roles, governance, vendors, subservice organisations, and complementary user entity controls.
- Significant changes during the period.
- Incident, availability, change, backup, recovery, and support processes.
- Control criteria, commitments, and exclusions.

The description must be complete and balanced. Do not omit material incidents, unavailable evidence, or dependencies that users need to evaluate controls.

## 4. Core common-criteria control areas

| Area | Control intent | Typical evidence |
|---|---|---|
| Governance and risk | Define responsibility, risk assessment, oversight, and control monitoring. | Policies; risk register; committee minutes; metrics; internal reviews. |
| Communication | Communicate security, availability, confidentiality, privacy, and change commitments. | Contracts; customer notices; training; policy acknowledgements. |
| Access | Provision, review, modify, and remove logical and physical access. | Access requests; reviews; IAM/PAM; termination samples; badge logs. |
| Security operations | Detect, respond to, and recover from threats and incidents. | Alerts; incident tickets; exercises; post-incident reviews; threat monitoring. |
| Change management | Authorise, test, approve, and implement system changes. | Change tickets; code review; test evidence; deployment logs; emergency changes. |
| Risk mitigation | Identify vulnerabilities, threats, vendors, and business continuity risks. | Scans; penetration tests; vendor assessments; BCP/DR tests; remediation. |
| Data protection | Protect data through classification, encryption, retention, disposal, and monitoring. | Data inventory; DLP; key records; deletion; access logs; privacy records. |
| Availability and resilience | Meet SLOs, monitor capacity, back up, recover, and communicate outages. | SLO reports; uptime; capacity; backup/restore; DR exercise; incidents. |
| Processing integrity | Validate input, processing, output, errors, reconciliations, and authorisation. | Interface logs; validation rules; reconciliation; error queues; processing reports. |
| Privacy | Govern notice, consent or lawful basis, rights, retention, disclosure, and breaches. | Privacy notice; processing register; request log; retention; vendor clauses; breach records. |

## 5. Type II period discipline

Evidence must demonstrate operation over the examination period. A policy approved on the first day does not prove it operated for the whole period. For recurring controls, maintain dated evidence for each occurrence or a justified sample. For continuous automated controls, prove configuration, monitoring, alert handling, and population completeness.

When a control changes, record the effective date, predecessor and successor, reason, risk impact, and how the auditor will assess each part of the period.

## 6. Complementary controls and subservice organisations

The service organisation must identify controls customers need to operate, such as configuring MFA, approving customer users, reviewing reports, or managing API credentials. It must also identify whether a subservice organisation is carved out or inclusive and explain the control impact.

Obtain current assurance reports, contracts, bridge coverage, exceptions, and responsibility matrices. A provider's certification does not automatically prove the service organisation's control operation.

## 7. Evidence quality

Evidence must show who performed the control, what population was covered, when it occurred, what was reviewed, what exceptions were found, and how they were resolved. Retain original system records where possible. Screenshots without date, scope, or provenance are weak evidence.

## 8. Management response

For each exception, state the condition, cause, risk, period, affected population, management response, corrective action, responsible owner, target date, and whether the exception affects the system description or customer commitments. Do not relabel a failed control as a “risk accepted” without explaining the impact on the report and user decisions.
