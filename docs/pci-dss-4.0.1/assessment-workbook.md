# PCI DSS v4.0.1 Banking Assessment Workbook

Use one row for each applicable PCI DSS requirement and sub-requirement in the official v4.0.1 reporting template. The rows below are control families to start planning; expand them to the exact sub-requirements and testing procedures for the engagement.

| Requirement family | Banking assessment procedure | Core evidence request | Interview / challenge prompts |
|---|---|---|---|
| 1 — Network security controls | Reconcile diagrams to inventories and rules; inspect approvals, periodic reviews, segmentation, cloud controls, and admin paths; validate a sample of denied and allowed flows. | Diagrams; firewall/routing/security-group exports; rule review; segmentation test; network standards; change tickets. | What changed since the last assessment? Which paths reach CDE from ATM, branch, DR, cloud, vendor, and internet? Who owns expired rules? |
| 2 — Secure configurations | Sample CDE and security-impacting devices across platforms; compare to approved baseline; verify defaults removed and exceptions governed. | Baselines; configuration exports; build records; vulnerability exceptions; wireless/cloud configuration; review sign-offs. | Which systems cannot meet the baseline? How is the exception time-bound and monitored? |
| 3 — Stored account data | Trace PAN from source to stores, caches, logs, backups, analytics, recordings, and disposal; inspect masking, unreadability, retention, and key lifecycle. | Data inventory; discovery results; retention policy; tokenisation/encryption; key ceremonies; HSM controls; deletion logs. | Where could PAN appear outside the CDE? Is SAD ever stored after authorisation? Who can administer keys and data separately? |
| 4 — Transmission cryptography | Sample external, internal, administrative, API, branch, ATM, provider, and DR paths; inspect protocols, certificates, trust stores, and key procedures. | Flow inventory; TLS/cipher configuration; certificate inventory; key-management standard; provider evidence; test output. | Which legacy paths remain? How are weak protocols detected and retired? |
| 5 — Malicious software | Establish covered asset population; inspect deployment, signatures/updates, alert handling, exceptions, and response; include servers and admin workstations. | Coverage reports; policy; exception list; alert tickets; update status; incident records. | What is excluded and why? How quickly are failures remediated? |
| 6 — Secure systems/software | Trace vulnerabilities from discovery to closure; sample changes and releases; inspect code review, dependency risk, separation, web testing, and emergency change. | Scan reports; remediation SLA; change tickets; SDLC; code review; inventory; penetration/web test; emergency review. | How are payment APIs and third-party libraries covered? What prevents emergency change becoming permanent bypass? |
| 6.4.3 — Payment-page scripts | Inventory scripts and authors; verify authorisation, integrity, change detection, alert investigation, and targeted risk analysis where used. | Script inventory; allowlist; integrity monitoring; alerts; change records; risk analysis. | Which third-party scripts can affect payment capture? Who investigates a script change? |
| 7 — Least privilege | Reconcile HR/role data, entitlement populations, privileged access, service accounts, and review results; test timely removal and approvals. | Role matrix; access requests; review attestations; PAM reports; joiner/mover/leaver samples; exceptions. | Are approvals before access? What is the business reason for each privileged role? |
| 8 — Identification/authentication | Test unique IDs, MFA, password settings, remote/vendor access, non-human accounts, credential storage/rotation, and termination. | IAM configuration; MFA coverage; PAM sessions; account inventory; lifecycle samples; service-account register. | Which accounts bypass MFA? Who owns service accounts? How are secrets rotated and monitored? |
| 9 — Physical access | Walk through data centres, card operations, branches, ATM operations, media stores, and DR; test visitor, badge, camera, media, and destruction processes. | Access logs; visitor records; CCTV retention; media inventory; destruction certificates; site procedures. | Are contractors escorted? How are lost media and decommissioned devices handled? |
| 10 — Logging/monitoring | Reconcile required log sources to SIEM; inspect time synchronisation, protection, review, alerts, retention, failed delivery, and PAN masking. | Log-source matrix; SIEM coverage; time source; daily reviews; alert cases; retention; immutable storage. | What happens when logs stop? Which events trigger escalation? Can logs expose PAN or credentials? |
| 11 — Security testing | Inspect authenticated and unauthenticated scans, penetration tests, segmentation, wireless, IDS/IPS, change detection, and remediation retests. | Scan schedules/reports; penetration test; segmentation validation; wireless test; IDS/IPS alerts; retest evidence. | Does testing cover APIs, cloud, DR, providers, and post-change paths? Who verifies findings are actually fixed? |
| 12 — Governance and programme | Test policy approval, risk analyses, scope confirmation, awareness, incident exercises, third-party responsibilities, executive oversight, and annual review. | Security policy; risk analyses; training; incident plan/exercise; TPSP register; AOCs/ROCs; scope review; committee minutes. | Who can accept risk? Which provider controls are shared? When was the incident plan exercised and what changed? |

## Assessment conclusion worksheet

| Measure | Result |
|---|---|
| Assessment period |  |
| Scope and CDE version/date |  |
| Requirements applicable |  |
| Requirements compliant |  |
| Partially compliant |  |
| Non-compliant |  |
| Not applicable with rationale |  |
| Not assessed / unknown |  |
| Open high or critical issues |  |
| Compensating controls |  |
| Evidence limitations |  |
| Executive conclusion |  |
| Approved by / date |  |
