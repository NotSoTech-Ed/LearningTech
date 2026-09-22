# Change Management Audit Workbook

## 1. Population reconciliation

| Source | Period | Population count | Unique key | Exported by/date | Hash or repository | Limitations |
|---|---|---:|---|---|---|---|
| Service management |  |  |  |  |  |  |
| Version control |  |  |  |  |  |  |
| CI/CD |  |  |  |  |  |  |
| Cloud audit |  |  |  |  |  |  |
| Database audit |  |  |  |  |  |  |
| Configuration management |  |  |  |  |  |  |
| Monitoring/incidents |  |  |  |  |  |  |
| Vendor/provider |  |  |  |  |  |  |

## 2. Change traceability worksheet

| Field | Result |
|---|---|
| Change ID |  |
| System/environment |  |
| Source commit, artifact digest, or configuration version |  |
| Requester and business reason |  |
| Risk/impact classification |  |
| Approval identity and timestamp |  |
| Developer identity |  |
| Deployer identity |  |
| Deployment target and timestamp |  |
| Test evidence and exact version tested |  |
| Production evidence and exact version deployed |  |
| Segregation result |  |
| Rollback/fallback evidence |  |
| Post-implementation validation |  |
| Related incident or problem |  |
| Exception and conclusion |  |

## 3. Interview questions

### Process owner

- What is the authoritative record of a change?
- How do you know the population is complete?
- Which changes are excluded from the process and why?
- How are configuration, infrastructure-as-code, feature flags, prompts, rules, and vendor changes classified?
- How are emergency changes prevented from becoming a permanent bypass?

### Developer and release manager

- Can a developer merge, approve, and deploy their own change?
- How are branches, pull requests, build artifacts, and deployment approvals protected?
- What happens when tests fail?
- How is the exact artifact in production identified?
- Who can alter pipeline definitions or bypass controls?

### Operations and platform owner

- How are direct production changes detected?
- Which audit logs record identity, target, before/after values, and time?
- How are failed deployments and rollbacks recorded?
- How is drift between declared infrastructure and deployed infrastructure identified?
- What happens when logging or monitoring is unavailable?

### Emergency-change owner

- What objective criteria make a change an emergency?
- Who can authorise it during an incident?
- What evidence is captured at the time?
- When is retrospective review completed?
- How often is the same type of emergency repeated?

### Auditor challenge questions

- Show a change that was approved before implementation, using an independent deployment source.
- Show a production deployment with no service-management record and explain it.
- Show a ticket closed as successful where the deployment failed.
- Show who could approve and deploy the same change.
- Show a change to the audit logging control itself.
- Show how deleted branches, force pushes, amended tickets, and changed approvals are detected.
- Show how vendor changes are included in the population.
- Show evidence that post-implementation validation actually occurred.

## 4. Exception evaluation

| Exception ID | Test | Condition | Isolated/systemic | Impact | Compensating control | Root cause | Conclusion |
|---|---|---|---|---|---|---|---|
| CMA-X-0001 |  |  |  |  |  |  |  |

## 5. Management report prompts

- Were the populations complete and independently reconciled?
- How many changes were unapproved, untraceable, late-approved, or deployed by conflicting roles?
- Which systems, identities, teams, providers, and periods are affected?
- Was any change to logging, identity, security controls, financial data, payment systems, or customer services involved?
- What immediate containment occurred?
- What sustainable remediation addresses the root cause?
- What residual risk requires formal acceptance?
