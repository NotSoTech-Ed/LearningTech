# Change Management Audit and Unapproved-Change Detection

This pack teaches an auditor, control owner, or GRC reviewer how to determine whether technology changes were authorised, tested, approved, deployed, and recorded accurately—and how to detect changes that bypassed the approved process.

It applies to banking applications, infrastructure, cloud services, databases, networks, security tooling, APIs, CI/CD pipelines, scripts, configuration, model or rules changes, and emergency changes.

## Pack contents

1. [`knowledge-base.md`](knowledge-base.md) — change-control concepts, identification processes, control objectives, and red flags.
2. [`assessment-method.md`](assessment-method.md) — step-by-step audit procedure, reconciliation, sampling, testing, and conclusions.
3. [`audit-workbook.md`](audit-workbook.md) — change traceability, interview questions, sample tests, and exception evaluation.
4. [`evidence-register.md`](evidence-register.md) — evidence, population, sample, exception, and remediation registers.
5. [`demonstration-guide.md`](demonstration-guide.md) — a complete banking example showing how to demonstrate one change and prove population completeness.
6. [`repository-audit-evidence.md`](repository-audit-evidence.md) — evidence generated from this repository's current Git branch.
7. [`repository-audit-report.md`](repository-audit-report.md) — scoped conclusion, findings, limitations, and management actions.

## Core audit question

For every material change, can the organisation prove:

1. **What** changed?
2. **Why** did it change?
3. **Who** requested and approved it?
4. **What** risk and impact were assessed?
5. **How** was it tested?
6. **Who** authorised production deployment?
7. **When and where** was it deployed?
8. **What** happened after deployment?
9. **Was the record protected from alteration?**
10. **Can the change be reversed or contained safely?**

Never rely on the change ticket alone. The strongest audit conclusion reconciles independent sources such as version control, CI/CD, cloud audit logs, endpoint or configuration-management data, database audit logs, service management records, and monitoring.

## Important boundary

This is an audit-readiness and learning aid, not a substitute for the organisation's approved policy, audit methodology, legal obligations, regulatory instructions, or external auditor requirements. Tailor scope, sampling, retention, and severity to the system, risk, reporting period, and applicable framework.
