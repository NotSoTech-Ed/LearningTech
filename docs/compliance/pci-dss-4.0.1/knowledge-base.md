# PCI DSS v4.0.1 Knowledge Base

## 1. What PCI DSS protects

PCI DSS is a baseline of technical and operational requirements designed to protect the payment account data environment. The assessment must identify where the account data exists, how it moves, who can access it, and which systems or services can influence the security of the environment.

### Payment data terms

| Term | Working meaning |
|---|---|
| Primary Account Number (PAN) | The payment card number. Stored PAN is account data and requires protection. |
| Cardholder data (CHD) | At minimum, PAN; it may also include cardholder name, expiration date, or service code when stored or processed with PAN. |
| Sensitive authentication data (SAD) | Authentication data such as full track data, card verification codes, or PIN/PIN blocks. Do not retain after authorisation, even if encrypted, except where PCI DSS explicitly permits otherwise. |
| CDE | People, processes, and technologies that store, process, or transmit CHD or SAD, plus components that may affect the security of CHD. |
| Connected-to system | A component that can communicate with the CDE and therefore may bring security risk into scope. |
| Security-impacting system | A component that does not directly handle CHD but can affect CDE security, such as identity, logging, vulnerability, network, or administrative systems. |
| Service provider | A third party that stores, processes, transmits CHD or can affect the security of a customer’s CDE. Confirm contractual and validation obligations. |

## 2. Version and applicability notes

PCI DSS v4.0.1 is a limited revision to v4.0, not a new baseline. Use the official v4.0.1 requirements, testing procedures, glossary, and reporting templates. Requirements designated future-dated in v4.0 became effective on **31 March 2025**; an assessment performed now must treat them as applicable unless the official instructions for the engagement say otherwise.

Do not infer compliance from a policy or a vendor certificate. Requirement applicability, scope, control implementation, evidence quality, and testing results must be established for the assessed period.

## 3. The 12 requirement domains

| # | Domain | Banking interpretation |
|---:|---|---|
| 1 | Network security controls | Govern segmentation, firewalls, cloud security groups, branch/ATM paths, remote access, and rule review. |
| 2 | Secure configurations | Harden operating systems, databases, network devices, endpoints, appliances, containers, cloud services, and HSM support components. |
| 3 | Protect stored account data | Minimise retention, mask and render PAN unreadable, protect keys, manage media, and prevent SAD storage. |
| 4 | Protect account data with strong cryptography during transmission | Secure public, private, API, administrative, branch, provider, and disaster-recovery paths. |
| 5 | Protect systems and software from malicious software | Cover malware-prone assets, anti-malware controls, exceptions, detection, response, and modern workloads where applicable. |
| 6 | Develop and maintain secure systems and software | Secure SDLC, vulnerability remediation, change control, web applications, payment APIs, and software inventory. |
| 7 | Restrict access by business need to know | Define roles, approve access, review privileges, and prevent excessive entitlements. |
| 8 | Identify users and authenticate access | Unique IDs, strong authentication, MFA, service accounts, remote access, privileged access, and lifecycle events. |
| 9 | Restrict physical access to account data | Secure branches, data centres, payment operations, media, visitor access, and destruction. |
| 10 | Log and monitor all access to systems and account data | Centralise, protect, review, alert on, retain, and investigate logs. |
| 11 | Regularly test security systems and processes | Vulnerability scans, penetration tests, segmentation validation, wireless testing, intrusion detection, and change-triggered testing. |
| 12 | Support information security with organisational policies and programs | Governance, targeted risk analysis, third parties, incident response, awareness, scope, and accountability. |

## 4. Requirement-by-requirement control knowledge

The table below is a control-design map, not a replacement for the official detailed testing procedures.

| Requirement | Control intent | Minimum banking evidence | Typical failure pattern |
|---|---|---|---|
| 1.1–1.5 | Define and maintain network security controls, configurations, diagrams, and segmentation. | Approved standards; current logical and data-flow diagrams; rule review records; segmentation tests; cloud/branch/ATM inventories. | Diagrams omit DR or provider paths; rules lack owners or expiry; “out of scope” is asserted but not tested. |
| 2.1–2.3 | Apply secure configurations and prevent vendor defaults. | Hardening baselines; build records; sampled configuration exports; exception register; wireless and cloud standards. | Baselines are generic; exceptions have no expiry; appliances and HSM support systems are omitted. |
| 3.1–3.3 | Minimise storage and protect stored account data and media. | Retention schedule; data discovery; masking/tokenisation evidence; key inventory; key ceremonies; media logs; deletion evidence. | PAN appears in logs, tickets, data lakes, backups, or call recordings; cryptographic keys are accessible to administrators without separation. |
| 4.1–4.2 | Protect CHD in transit and manage cryptographic keys and certificates. | TLS standards; certificate inventory; sampled flows; cipher/configuration evidence; key-management procedures; provider attestations. | Internal traffic is assumed trusted; expired certificates; weak protocols remain on legacy ATM or provider connections. |
| 5.1–5.4 | Prevent, detect, and address malicious software. | Asset applicability analysis; endpoint/anti-malware coverage; alert and exception reports; malware response records. | Coverage excludes appliances, servers, VDI, or admin workstations; exceptions are indefinite. |
| 6.1–6.4 | Maintain vulnerability processes and secure development/change practices. | Vulnerability SLAs; scans; code review; SDLC; change tickets; dependency inventory; web-application testing; production separation. | Fix dates are measured from ticket creation rather than discovery; emergency changes bypass review; payment APIs lack security testing. |
| 6.4.3 | Change and tamper-detection mechanisms for payment pages where applicable. | Payment-page inventory; authorised script list; integrity monitoring; change review; alert investigations; targeted risk analysis if used. | Web scripts are unknown, third-party scripts are unmanaged, or monitoring alerts are not investigated. |
| 7.1–7.3 | Restrict access by need to know and least privilege. | Role catalogue; approval records; joiner/mover/leaver samples; quarterly reviews; privilege recertification; service-account ownership. | Entitlements are approved after access; generic IDs; business roles do not map to technical privileges. |
| 8.1–8.6 | Identify users, authenticate access, and manage credentials and MFA. | Identity inventory; MFA policy; authentication settings; privileged session logs; password and service-account controls; lifecycle samples. | Shared admin accounts; MFA bypasses; non-human credentials never rotate; remote vendor access is permanently enabled. |
| 9.1–9.5 | Protect facilities, media, and devices physically. | Data-centre/branch controls; badge and visitor logs; CCTV retention; media inventory; destruction certificates; delivery logs. | DR sites and branch back rooms are excluded; visitor logs do not identify escort; media destruction is not evidenced. |
| 10.1–10.7 | Generate, protect, review, retain, and respond to security logs. | Log-source inventory; SIEM coverage; time synchronisation; daily review records; alert cases; retention configuration; immutable storage. | Logs are collected but not reviewed; time sources differ; failed log delivery is silent; PAN appears in event payloads. |
| 11.1–11.6 | Test controls and detect unauthorised changes or attacks. | Scan reports; penetration tests; segmentation tests; wireless tests; IDS/IPS/SIEM alerts; change-detection evidence; remediation validation. | Tests omit authenticated scanning, cloud, APIs, CDE-to-provider paths, or post-change validation. |
| 12.1–12.10 | Govern the programme, people, third parties, incidents, and scope. | Security policy; targeted risk analyses; responsibilities; awareness records; TPSP register and AOCs; incident plan/exercises; annual scope confirmation; executive reporting. | Policy exists without implementation; risk analyses lack methodology; provider responsibility is unclear; incident plans are not tested. |

## 5. Targeted risk analysis

Where PCI DSS permits an entity to define a frequency or use a risk-based approach, document:

1. The asset, process, or requirement being varied.
2. The threat and business impact.
3. The likelihood and impact rationale.
4. Factors considered, data used, and assumptions.
5. The chosen frequency or alternate control.
6. The accountable approver and independent challenge.
7. Monitoring indicators, review date, and trigger for reassessment.

A risk analysis cannot be used to waive a requirement. It supports a permitted approach only when the applicable PCI DSS requirement and reporting instructions allow it.

## 6. Evidence quality rules

Good evidence is attributable, complete, current for the assessment period, reproducible, protected from alteration, and linked to a control and population. Prefer system-generated records over screenshots. A screenshot may demonstrate configuration but rarely proves population completeness or sustained operation.

For every item, record source, owner, extraction date, period covered, population, selection method, reviewer, hash or repository reference where appropriate, and any limitation.
