# SOX ITGC Knowledge Base

## 1. What SOX compliance establishes

SOX Section 404 requires management to assess internal control over financial reporting (ICFR), with external auditor attestation requirements depending on the issuer and applicable rules. IT is in scope when technology controls or automated processing can affect financial reporting.

The objective is not to prove that every technology control is perfect. It is to obtain reasonable assurance that material misstatements in financial reporting are prevented or detected on a timely basis.

## 2. Core terms

| Term | Working meaning |
|---|---|
| ICFR | A process designed to provide reasonable assurance regarding reliability of financial reporting and preparation of financial statements for external purposes. |
| Significant account or disclosure | An account/disclosure with a reasonable possibility of material misstatement, considering size and qualitative factors. |
| Relevant assertion | Financial statement assertion such as existence, completeness, accuracy, valuation, rights and obligations, occurrence, or presentation. |
| Key control | A control relied on to prevent or detect a material misstatement; failure may affect the ICFR conclusion. |
| ITGC | Foundational technology controls commonly covering access, change, operations, development, and technology governance. |
| Application control | Automated or IT-dependent manual control in an application, such as validation, interface reconciliation, workflow approval, or completeness check. |
| Service organisation | A provider whose services or controls are relevant to the entity's ICFR. |
| Complementary user entity control | A control the customer must operate for the service provider's control objectives to be achieved. |
| Deficiency | A control deficiency; evaluate severity individually and in combination with other deficiencies. |
| Material weakness | A deficiency or combination of deficiencies creating a reasonable possibility that a material misstatement will not be prevented or detected on a timely basis. |
| Significant deficiency | A deficiency or combination of deficiencies less severe than a material weakness but important enough to merit attention by those charged with governance. |

## 3. SOX scoping model

Begin with financial statement risks, not the technology inventory:

1. Identify material accounts, disclosures, significant estimates, and relevant assertions.
2. Identify key business processes: record-to-report, procure-to-pay, order-to-cash, treasury, payroll, lending, impairment, regulatory reporting, and consolidation where relevant.
3. Map processes to applications, databases, interfaces, reports, spreadsheets, infrastructure, cloud services, and service organisations.
4. Identify IT-dependent manual controls and automated application controls.
5. Include systems that can create, change, calculate, transfer, approve, post, or report financial data.
6. Document excluded systems and the risk-based rationale.

### Banking-specific scoping considerations

- Core banking, general ledger, sub-ledgers, treasury, markets, liquidity, impairment, and provisioning platforms.
- Regulatory and financial reporting data warehouses, management reporting, and consolidation tools.
- Loan origination, card, payments, fees, interest, commissions, and customer compensation processes.
- End-user computing, spreadsheets, scripts, robotic process automation, and data extracts used in reporting.
- Cloud platforms, managed databases, SaaS finance systems, data centres, and disaster-recovery environments.
- Interfaces between customer, product, risk, finance, and regulatory systems.
- Service organisation controls and complementary controls for hosted platforms.

## 4. Core ITGC domains

| Domain | Control objective | Typical evidence |
|---|---|---|
| Logical access | Only authorised users receive appropriate access, privileged access is controlled, and access is removed or changed timely. | User listings; role matrix; approvals; joiner/mover/leaver samples; privileged access reviews; MFA/PAM records. |
| Change management | Changes affecting financial systems are authorised, tested, approved, migrated, and traceable. | Change tickets; approvals; test evidence; segregation; migration logs; emergency change review. |
| IT operations | Processing is complete, accurate, monitored, recoverable, and supported by reliable jobs, backups, incidents, and interfaces. | Job schedules; failed-job logs; reconciliations; incident records; backup/restore tests; interface monitoring. |
| SDLC and development | New or materially changed financial applications are securely designed, tested, approved, and separated from production. | Requirements; code review; test results; release approvals; repository access; production deployment logs. |
| Computer operations and infrastructure | Systems are configured, available, monitored, and protected against unauthorised change. | Configuration baselines; monitoring; vulnerability records; capacity; patching; DR evidence. |
| Data and reporting | Reports, interfaces, and data transformations used in ICFR are complete, accurate, authorised, and reproducible. | Report inventories; query logic; reconciliation; report access; end-user computing controls; data lineage. |
| Third parties | Outsourced controls are evaluated and user responsibilities are performed. | SOC 1 reports; bridge letters; contracts; gap assessments; complementary user controls; issue follow-up. |

## 5. Control design principles

Every key control should state:

- Risk and relevant financial statement assertion.
- Control objective and precise activity.
- Population and source system.
- Owner and independent reviewer.
- Frequency and timing.
- Evidence retained and retention period.
- What happens when the control fails.
- Segregation of duties and conflict resolution.
- Dependencies on other controls, reports, interfaces, or providers.

A policy or system capability is not evidence that the control operated.

## 6. Deficiency concepts

Evaluate a deficiency using likelihood and magnitude, including qualitative factors, not only the value of a single transaction. Consider:

- Size and nature of accounts or disclosures affected.
- Susceptibility to fraud or management override.
- Complexity and subjectivity of accounting.
- Volume, duration, frequency, and distribution of exceptions.
- Whether the control is preventive or detective.
- Whether compensating controls operated effectively.
- Whether the issue affects multiple systems, processes, or reporting periods.
- The possibility that a misstatement could be material before detection.

Document the accounting and audit impact separately from the technology root cause.
