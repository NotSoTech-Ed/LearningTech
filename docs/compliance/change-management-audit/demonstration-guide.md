# Demonstrating Change Management: Banking Example

This guide shows how to demonstrate change management to an auditor using one traceable banking change. The example is fictional and uses sanitised identifiers. Replace it with evidence from the assessed environment; do not manufacture records or backfill approvals.

## 1. The example change

**Scenario:** The bank updates the transaction-limit validation rule in its payments API after a regulatory-approved product change. The API supports mobile banking, internet banking, and branch-assisted transactions. The change affects a production application, a configuration repository, a CI/CD pipeline, monitoring rules, and a customer-facing service.

| Field | Example |
|---|---|
| Change ID | CHG-2026-01482 |
| Type | Normal, high-risk |
| Service | Retail payments API |
| Business reason | Implement approved transaction-limit change |
| Risk | Incorrect limits could allow unauthorised exposure or reject valid transactions |
| Affected components | API service, rules configuration, database feature flag, monitoring alert |
| Requester | Payments Product Owner |
| Developer | Payments Engineering |
| Approver | Change Advisory Board delegate and service owner |
| Deployer | Controlled release service account |
| Planned window | 2026-09-18 22:00–23:00 IST |
| Rollback | Restore prior artifact and feature-flag value |
| Validation owner | Payments Operations |

The example is useful because it is not merely a code change. It includes business approval, configuration, automated deployment, customer impact, monitoring, and rollback.

## 2. What the auditor needs to prove

The demonstration should answer the following chain without relying on one screenshot:

```text
Business need
  -> risk and impact assessment
  -> approved change record
  -> reviewed source/configuration
  -> tested artifact
  -> authorised deployment
  -> production evidence
  -> post-change validation
  -> closure and monitoring
```

For each link, show the identifier that connects it to the next link. The strongest identifiers are change ID, pull request ID, commit SHA, build ID, artifact digest, deployment ID, environment, actor, and timestamp.

## 3. Evidence package for CHG-2026-01482

### 3.1 Business request and scope

Show:

- Approved product or regulatory requirement.
- Business owner and accountable service owner.
- Affected products, channels, customers, data, and legal entities.
- Impact assessment, dependencies, communication plan, and implementation window.
- Classification as high-risk and the reason for that classification.

**Auditor conclusion supported:** the change had a legitimate purpose and its scope was understood before implementation.

### 3.2 Change record

Show the native service-management record, not a retyped summary:

- Requester and creation timestamp.
- Description and affected configuration or code.
- Risk, impact, priority, and change type.
- Test plan and acceptance criteria.
- Rollback or fallback plan.
- Required approvers.
- Approval timestamps.
- Planned and actual implementation times.
- Related incident, problem, release, and deployment IDs.
- Immutable history or audit trail showing edits and status transitions.

**Key test:** approval must precede implementation for a normal change. A later approval does not repair a missing pre-approval; record it as an exception unless the emergency process genuinely applies.

### 3.3 Source and configuration evidence

Show:

- Pull request `PR-8841` linked to `CHG-2026-01482`.
- Reviewers and review timestamps.
- Commit SHA `7ac91e2`.
- Protected branch settings.
- Files or configuration values changed.
- Evidence that the reviewed commit is the commit built and deployed.
- No unreviewed direct commit or force-push was used to bypass review.

For a rule or feature flag change, include before/after values and the rationale. For infrastructure-as-code, include the plan, approval, apply output, and state version.

**Auditor conclusion supported:** the production change was traceable to reviewed source or configuration.

### 3.4 Testing evidence

Show:

- Test environment and version tested.
- Functional tests for valid and invalid transaction limits.
- Negative tests for boundary values and bypass attempts.
- Regression tests for mobile, internet, and branch channels.
- Security and authorisation tests where the rule affects access or transaction risk.
- Performance and rollback test where the service is critical.
- Test result, tester identity, timestamp, defects, and disposition.
- Business acceptance that the result meets the approved requirement.

The tested version must match the deployed version by commit SHA, build ID, artifact digest, or an equivalent reliable identifier.

**Weak evidence:** “QA approved” in a ticket with no test scope, version, result, or evidence.

### 3.5 Approval and segregation evidence

Demonstrate:

- The requester's role and business authority.
- The technical reviewer's role.
- The change approver's authority.
- The deployer's identity or controlled service account.
- That no individual performed incompatible steps without an approved exception.
- How break-glass or service-account use is monitored.

A typical acceptable separation is:

| Activity | Actor |
|---|---|
| Request and business justification | Payments Product Owner |
| Development | Payments Engineer |
| Code review | Senior Engineer / Security Reviewer |
| Risk approval | Change Advisory Board delegate |
| Production deployment | Release service account |
| Post-change validation | Payments Operations |

The service account does not create independence by itself. Verify who can alter the pipeline, approve deployments, or impersonate the service account.

### 3.6 CI/CD and deployment evidence

Show the native pipeline record:

- Pipeline run ID and repository/branch.
- Commit SHA and artifact digest.
- Build result and test gates.
- Approval gate and approver.
- Target environment.
- Deployment actor.
- Start and completion timestamps with timezone.
- Result, rollback, or failure status.
- Deployment manifest and changed components.

Compare the pipeline record with:

- Change ticket window.
- Cloud or platform audit log.
- Application release marker.
- Monitoring event.
- Incident or rollback record.

**Auditor conclusion supported:** the approved artifact was deployed to the approved target during the approved window.

### 3.7 Production and independent validation

Show:

- Production configuration or release state after deployment.
- Health checks and transaction-limit test results.
- Monitoring dashboard or release marker.
- Error, latency, fraud, and customer-impact metrics.
- Operations sign-off.
- Any incident, rollback, or customer communication.

Validation should be specific. “No issues reported” is weaker than “Operations tested the four boundary cases, reconciled the deployed version to build 4418, reviewed error rate for 30 minutes, and found no exception.”

### 3.8 Closure and retention

Show:

- Actual implementation result.
- Closure checklist.
- Post-implementation review for the high-risk change.
- Unresolved defects and follow-up actions.
- Links to related incident or problem records.
- Evidence retention location and access controls.
- Final status history.

Do not close the ticket merely because deployment succeeded. The change is complete when the outcome, monitoring, exceptions, and follow-up are recorded.

## 4. End-to-end demonstration script

Use this sequence during an audit walkthrough:

1. Open the change record and state the business purpose, scope, risk, and planned window.
2. Show the approval history and point out that required approvals predate deployment.
3. Follow the pull-request link to the reviewed commit.
4. Follow the commit to the build and artifact digest.
5. Open test evidence for that exact version and explain failed tests or defects.
6. Show the deployment approval, target, identity, timestamp, and result.
7. Reconcile the deployment to the cloud/platform audit log.
8. Show production validation and monitoring after deployment.
9. Show closure, post-implementation review, and any related incident.
10. Explain how the same evidence would be obtained for the wider population.

The walkthrough should be performed by the control owner, with the auditor independently following the links. Do not navigate only through a prepared slide deck.

## 5. Demonstrating population completeness

A good single-change walkthrough does not prove that all changes were controlled. Demonstrate completeness separately for the assessment period.

### Example reconciliation

| Source | Count | Matching key | Result |
|---|---:|---|---|
| Service-management normal/emergency changes | 1,248 | Change ID | Baseline |
| CI/CD production deployments | 1,263 | Deployment ID, commit, target, time | 15 not matched |
| Cloud audit events | 1,311 | Actor, resource, event, time | 63 not matched |
| Database audit events | 84 | Actor, object, statement, time | 4 not matched |
| Configuration-management snapshots | 1,257 | Asset, version, timestamp | 9 not matched |

The unmatched items become investigation queues. For each, classify:

- Duplicate or technical event.
- Approved change with missing linkage.
- Vendor or platform maintenance.
- Standard change.
- Emergency change.
- Direct or unauthorised production change.
- Logging or population limitation.

If the 15 unmatched deployments include direct production changes, expand testing and assess whether the issue is systemic. Do not report “1,248 changes tested” without explaining the 15 unmatched deployments.

## 6. Example exception

**Condition:** Deployment `DEP-77219` changed a production firewall rule at 02:14 IST. It appears in the cloud audit log and was performed by an administrator, but no approved change record existed before implementation. A ticket was created at 09:10 IST.

**Initial conclusion:** Unapproved or untraceable production change; not repaired by the later ticket.

**Questions to resolve:**

- Was there an active incident requiring emergency action?
- Who authorised the action at 02:14?
- Was the change minimal and reversible?
- Was the rule change recorded in the platform audit log?
- Was retrospective emergency review completed within policy?
- Was the rule validated and removed or normalised?
- Has the same administrator performed similar direct changes?
- Could the administrator alter or delete the evidence?
- Did the change affect CDE, financial reporting, customer service, or security monitoring?

**Finding structure:**

| Field | Example |
|---|---|
| Requirement/control | Production changes require pre-approval; emergency changes require documented authority and review. |
| Condition | Firewall change occurred before any approved record existed. |
| Risk | Unauthorised rule may expose systems or disrupt protective controls. |
| Root cause | Direct administrative access and incomplete emergency linkage. |
| Immediate action | Validate current rule, restrict access, preserve logs, and review related changes. |
| Sustainable action | Enforce controlled deployment, emergency workflow, privileged-session monitoring, and reconciliation alerts. |
| Closure evidence | Retest direct-change detection and emergency approval across a later period. |

## 7. Auditor questions that expose weak demonstrations

- Show the population before selecting your sample.
- What independent source would reveal a deployment missing from the ticketing system?
- Which timestamp is authoritative, and what timezone does it use?
- Can an administrator alter the ticket approval history?
- Can a developer approve their own pull request or pipeline?
- How do you detect changes made through a console, script, API, or vendor?
- What happens when the CI/CD pipeline is unavailable?
- How are standard changes prevented from becoming a broad bypass?
- How many emergency changes were later normalised, and how many repeated the same cause?
- Show a failed change and a rollback, not only successful changes.
- Show how a change to logging, IAM, firewall, or monitoring is itself controlled.
- What evidence proves that the tested artifact is the production artifact?
- What limitation prevents you from concluding that the population is complete?

## 8. Demonstration conclusion template

> For the period **[period]**, we assessed **[systems/change types]** against **[policy/framework criteria]**. We reconciled **[sources]** and identified **[population limitations/unmatched items]**. For the sampled changes, **[approval, segregation, testing, deployment, and validation conclusion]**. Exceptions were **[count/severity]**, including **[material issue]**. Based on the evidence available, change management is **[effective/partially effective/not effective/not concluded]** for **[scope]**, subject to **[limitations and remediation]**.

Do not claim that no unauthorised changes occurred unless the population, logs, scope, and testing support that conclusion.
