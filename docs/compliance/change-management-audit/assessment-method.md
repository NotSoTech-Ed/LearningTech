# Change Management Audit Assessment Method

## Phase 1 — Define scope and criteria

Record:

- Entity, reporting period, systems, environments, and locations.
- Applicable policies, standards, regulatory commitments, and framework criteria.
- In-scope change types, including code, configuration, infrastructure, data, rules, model/prompt, and vendor changes.
- Critical services, financial-reporting systems, CDE components, customer-impacting systems, and security-impacting systems.
- Authoritative source systems, log-retention periods, timezones, and known limitations.

Do not assess “change management” as one undifferentiated control. Separate normal, standard, emergency, privileged, direct, vendor, and automated pipeline changes where their risks differ.

## Phase 2 — Understand the process

Walk one successful normal change, one failed or rolled-back change, one emergency change, and one configuration or infrastructure change from request through closure.

Document:

1. Request and business reason.
2. Risk and impact classification.
3. Test plan and result.
4. Approval and segregation.
5. Artifact or configuration version.
6. Deployment identity, target, and timestamp.
7. Monitoring and validation.
8. Rollback or recovery.
9. Closure and lessons learned.

Identify which system is the source of truth for each step. If no source is authoritative, record a governance gap.

## Phase 3 — Obtain and reconcile populations

Request period-complete exports from service management, version control, CI/CD, cloud audit, database, configuration, security, vendor, monitoring, and incident systems as applicable.

### Reconciliation procedure

1. Normalise timestamps to a declared timezone.
2. Remove only documented technical duplicates; never silently deduplicate distinct deployments.
3. Match by change ID, commit, artifact digest, deployment ID, actor, target, and time window.
4. Produce unmatched items on both sides.
5. Investigate every high-risk or privileged unmatched item.
6. Expand the population when an omission or systemic weakness is found.
7. Retain the original exports and reconciliation logic.

## Phase 4 — Select samples

Use a risk-based sample that includes:

- Critical and high-risk changes.
- Changes to authentication, security controls, financial reporting, payment, customer, and regulatory systems.
- Emergency, failed, rolled-back, and direct production changes.
- Changes by privileged or service identities.
- Changes near reporting cut-offs or major releases.
- Random selections from normal and standard populations.
- Items from every material platform, team, location, and provider.

The sample is not a substitute for population completeness. Test the completeness of the population first.

## Phase 5 — Test each sampled change

For each item, trace the same identifier across independent sources and record pass, exception, or not applicable:

| Test | Pass condition |
|---|---|
| Scope | The item is within the defined system and period. |
| Intent | Business/technical purpose and affected assets are documented. |
| Risk | Impact, dependencies, security, data, resilience, and rollback are assessed proportionately. |
| Approval | Authorised approval predates implementation, unless emergency policy applies. |
| Segregation | Conflicting roles are prevented or formally controlled. |
| Testing | Evidence relates to the exact version or configuration deployed. |
| Artifact traceability | Source, build, artifact, and deployment can be connected. |
| Deployment | Identity, target, window, result, and actual version are recorded. |
| Validation | Outcome was checked and exceptions handled. |
| Closure | Ticket, evidence, incidents, rollback, and follow-up are complete. |

## Phase 6 — Evaluate exceptions

For each exception, establish:

- Exact condition, system, identity, timestamp, and affected change.
- Whether it is isolated, recurring, or systemic.
- Security, availability, financial, regulatory, privacy, customer, and operational impact.
- Whether the change was later approved, and whether retrospective approval is allowed or merely masks a failure.
- Compensating controls and their evidence.
- Root cause, accountable owner, due date, and sustainable treatment.

Do not treat the absence of a known incident as proof that an unauthorised change was harmless.

## Phase 7 — Conclude and report

Report separately on:

- Population completeness and reconciliation quality.
- Design effectiveness.
- Operating effectiveness by change type.
- Unapproved or untraceable changes.
- Segregation-of-duties conflicts.
- Emergency-change governance.
- Audit-log integrity and retention.
- Repeat exceptions and root causes.
- Residual risk and management decisions.

An audit conclusion must state limitations. “No exceptions identified” is not equivalent to “no unauthorised changes occurred” if source populations were incomplete.
