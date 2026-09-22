# AAIR Knowledge Base

## 1. Why AI risk is different

AI systems can change behaviour as data, prompts, models, vendors, and operating contexts change. Risk management must therefore address not only confidentiality, integrity, and availability, but also validity, explainability, fairness, robustness, privacy, misuse, human oversight, accountability, and the consequences of automation.

An AI risk opinion should distinguish:

- **Use-case risk:** whether the intended decision or outcome is appropriate.
- **Data risk:** quality, provenance, representativeness, rights, privacy, poisoning, and leakage.
- **Model risk:** suitability, assumptions, training, validation, drift, bias, robustness, and performance.
- **Technology risk:** access, infrastructure, dependencies, interfaces, availability, and change.
- **Process and people risk:** human oversight, skills, incentives, escalation, and over-reliance.
- **Third-party and ecosystem risk:** foundation models, APIs, datasets, cloud, open source, and concentration.
- **Legal, regulatory, ethical, and reputational risk:** obligations, affected persons, explainability, and trust.

## 2. Domain 1 — AI Risk Governance and Framework Integration (37%)

### Governance building blocks

| Building block | Practical control |
|---|---|
| Strategy and inventory | Maintain an approved inventory of AI use cases, models, owners, purpose, risk tier, data, provider, and lifecycle state. |
| Accountability | Assign business owner, model owner, data owner, technology owner, risk challenge, privacy/legal, security, and approval authority. |
| Policy and standards | Define acceptable use, prohibited use, human oversight, data requirements, model validation, monitoring, incident response, and exceptions. |
| Risk appetite | Set thresholds for performance, bias, privacy, explainability, autonomy, availability, and residual risk. |
| Integration | Map AI risks into enterprise risk taxonomy, registers, control library, third-party risk, change management, and internal audit plans. |
| Independent challenge | Separate development, business approval, validation, and risk acceptance where the impact warrants it. |
| Reporting | Give management and the board meaningful metrics, emerging risks, exceptions, incidents, and decisions required. |

### Governance questions

1. What decision is being automated or augmented, and who is affected?
2. Is the use case lawful, necessary, proportionate, and consistent with policy?
3. Who can stop, override, or retire the system?
4. What evidence supports the risk tier and approval?
5. How are model, data, prompt, provider, and use-case changes detected?
6. How does the AI risk register connect to enterprise risk acceptance?

## 3. Domain 2 — AI Life Cycle Risk Management (21%)

Apply controls across the full life cycle:

1. **Ideation and intake:** purpose, prohibited uses, impact assessment, initial risk tier, and accountable owner.
2. **Data acquisition and preparation:** provenance, rights, privacy, quality, lineage, representativeness, labelling, and poisoning controls.
3. **Design and development:** architecture, model choice, secure coding, prompt design, threat modelling, explainability, and documentation.
4. **Validation and approval:** independent validation, performance thresholds, bias/fairness analysis, robustness, privacy, red-team testing, and human oversight.
5. **Deployment:** release approval, access, environment separation, fallback, user training, monitoring, and customer communication.
6. **Operation:** drift, performance, incidents, access, output review, data changes, vendor changes, and periodic reassessment.
7. **Retirement:** data retention, model and prompt disposal, dependency removal, customer communication, and lessons learned.

### Key AI control concepts

- **Model inventory:** model version, purpose, owner, input/output, training data, provider, location, dependencies, and approval state.
- **Model card or system record:** intended use, limitations, evaluation results, assumptions, known risks, and monitoring.
- **Data lineage:** source, transformation, use, retention, access, and deletion.
- **Human-in-the-loop:** a person has meaningful authority, competence, context, and time to review or override.
- **Drift:** material change in data, relationships, behaviour, performance, or context.
- **Robustness:** resilience to expected variation, adversarial input, prompt injection, data poisoning, and operational failure.
- **Explainability:** an explanation appropriate to the decision, audience, impact, and available evidence; not merely a technical model description.

## 4. Domain 3 — AI Risk Program Management (42%)

### Scenario identification and assessment

Use threat modelling and impact analysis to consider hallucination, prompt injection, data poisoning, model extraction, membership inference, sensitive-data leakage, harmful automation, bias, drift, deepfakes, unsafe autonomy, vendor outage, and misuse.

### Risk treatment

Choose among avoid, reduce, transfer/share, or accept. Controls should be proportionate to impact and include preventive, detective, corrective, and compensating measures. A control is not a treatment unless it changes exposure and can be evidenced.

### AI control management

Evaluate, select, validate, monitor, and improve controls. Test both technical controls and organisational controls such as approval, training, escalation, and accountability.

### Metrics and reporting

Useful metrics connect AI behaviour to risk:

- Inventory coverage and overdue risk reviews.
- High-impact use cases without independent validation.
- Performance, drift, bias, privacy, security, and availability threshold breaches.
- Human override rate and unresolved override failures.
- Third-party model changes and concentration exposure.
- Incidents by severity, detection time, containment time, and recurrence.
- Open high-risk actions by age, owner, and residual risk.

### Supply chain, incident response, BIA, and DR

Assess model providers, datasets, APIs, cloud platforms, open-source components, managed services, and downstream users. Contracts should address data use, training, retention, security, change notice, audit rights, incident notification, resilience, exit, and responsibility.

AI incidents should have playbooks for unsafe output, privacy leakage, adversarial manipulation, integrity failure, discriminatory outcome, provider outage, and loss of human control. Business impact analysis must identify critical decisions, recovery objectives, fallback procedures, manual operation, and safe shutdown.

## 5. Practical assessment principle

The strongest answer to an AI risk problem starts with **impact and accountability**, then applies proportionate governance, life-cycle controls, monitoring, human oversight, and evidence. Do not jump directly to a tool or model change before clarifying the decision, affected parties, and risk tolerance.
