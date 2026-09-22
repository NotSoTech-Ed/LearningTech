# Change Management Audit Knowledge Base

## 1. What the control is intended to achieve

Change management should prevent unauthorised, inadequately tested, or untraceable changes from introducing security, availability, processing, financial-reporting, regulatory, or customer harm.

The control is not “tickets exist.” It is a connected process that preserves:

- Authorised business and technical purpose.
- Risk, impact, dependency, and rollback assessment.
- Appropriate testing and evidence.
- Segregation between request, approval, development, deployment, and verification where risk requires it.
- Accurate production deployment records.
- Monitoring and post-change validation.
- Emergency-change governance.
- Immutable or access-controlled audit evidence.

## 2. Change categories

| Category | Expected treatment |
|---|---|
| Standard change | Pre-authorised, repeatable, low-risk procedure with defined scope, owner, test, and rollback. It is not a way to avoid records. |
| Normal change | Assessed and approved before implementation according to risk and impact. |
| Major/high-risk change | Enhanced testing, stakeholder approval, implementation plan, fallback, communication, and post-implementation review. |
| Emergency change | Immediate action may be necessary, but the reason, authority, evidence, retrospective review, and normalisation must be recorded. |
| Failed or backed-out change | Failure, decision, customer/system impact, rollback, root cause, and follow-up must be documented. |
| Configuration or content change | Includes rules, thresholds, scripts, feature flags, prompts, model versions, firewall rules, IAM policies, database schemas, and infrastructure-as-code—not only compiled code. |

## 3. Change identification: build the true population

The central audit risk is an incomplete population. Start with the period, systems, environments, and change types, then reconcile multiple independent sources.

### Source systems to compare

| Source | What it can reveal |
|---|---|
| IT service-management tool | Requested, approved, scheduled, and closed changes. |
| Version-control platform | Commits, pull requests, branches, reviewers, merges, tags, and force pushes. |
| CI/CD platform | Builds, artifacts, approvals, pipeline runs, deployment targets, identities, and failures. |
| Cloud audit logs | Infrastructure, IAM, security groups, functions, storage, secrets, and configuration changes. |
| Database audit logs | DDL, privileged data changes, jobs, stored procedures, and direct production access. |
| Endpoint and configuration management | Software, patches, configuration, agents, and device changes. |
| Network and security tooling | Firewall, WAF, DNS, proxy, rule, certificate, detection, and policy changes. |
| Infrastructure-as-code state | Declared versus deployed infrastructure and drift. |
| Monitoring and incident systems | New alerts, deployment markers, outages, rollback, and change-related incidents. |
| Vendor/provider records | SaaS releases, maintenance, emergency changes, and responsibility evidence. |

### Population reconciliation logic

Create a stable identifier where possible, then compare:

- Changes in the service-management population but absent from deployment records.
- Deployments or commits absent from approved change records.
- Production actors or timestamps with no matching ticket or approval.
- Closed tickets with no successful deployment or validation.
- Multiple deployments linked to one ticket without explanation.
- One deployment linked to multiple unrelated tickets.
- Changes performed outside the approved window.
- Changes made by identities not authorised for the environment.
- Direct production changes followed by a ticket created later.

The differences are not automatically findings. They are investigation queues. Resolve each difference with evidence and record the conclusion.

## 4. Control objectives and audit questions

### Planning and risk

- Does every in-scope change have a clear description and business or operational reason?
- Does the record identify affected services, data, dependencies, downtime, security impact, and rollback?
- Is the risk classification appropriate to the change and not simply selected to obtain faster approval?
- Are regulatory, PCI, financial-reporting, privacy, resilience, and customer impacts considered?

### Approval and segregation

- Was approval obtained before implementation?
- Was the approver authorised and independent enough for the risk?
- Could the requester, developer, or deployer approve their own change?
- Are privileged or break-glass accounts controlled and reviewed?
- Are electronic approvals attributable, timestamped, and protected from alteration?

### Development and testing

- Is the deployed artifact traceable to reviewed source code or configuration?
- Was testing performed in an appropriate non-production environment?
- Does testing cover functional, security, performance, resilience, data migration, and integration risks as relevant?
- Were failed tests and defects resolved or formally accepted before deployment?
- Was test evidence retained from the actual version deployed?

### Deployment and validation

- Does the deployment identity match an authorised person or controlled service account?
- Do deployment logs show target, version, start/end time, result, and artifact?
- Was the implementation within the approved window and scope?
- Was post-implementation validation performed by an appropriate person or control?
- Were monitoring, customer communication, rollback, and incident procedures used where needed?

### Emergency and direct changes

- What made the change an emergency?
- Who authorised it at the time?
- Was the minimum safe change made?
- Was evidence captured during or immediately after implementation?
- Was retrospective approval or review completed within policy?
- Was the change brought back into normal configuration and source control?
- Are repeated “emergencies” actually a planning or capacity problem?

## 5. Red flags

- Ticket created after deployment.
- Approval timestamp after implementation.
- Identical approval comments across unrelated changes.
- Approver, developer, and deployer are the same person without a documented exception.
- Production deployment from an unprotected branch or personal workstation.
- Force-pushed or deleted branches around the deployment date.
- Pipeline approval performed by an account also able to modify the pipeline.
- Closed ticket has no deployment log, artifact, test result, or validation.
- One “standard change” used for materially different activities.
- Emergency changes cluster around month-end, quarter-end, or audit dates.
- Repeated manual edits in production.
- Audit logs are disabled, incomplete, mutable, or retained for less than the assessed period.
- Evidence is a screenshot without source, timestamp, population, or version.
- Change-related incidents are not linked back to change records.

## 6. What counts as persuasive evidence

Evidence should be attributable, complete, time-relevant, reproducible, access-controlled, and linked to the exact change and environment. Prefer exports or native records over screenshots. Preserve the extraction date, query or filter, timezone, population, reviewer, and limitations.

No single source proves the whole control. A ticket may prove intent, while a deployment log proves execution and a monitoring record proves outcome.
