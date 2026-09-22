# PCI DSS v4.0.1 Banking Compliance Pack

This pack is a practical knowledge base and assessment method for a banking institution that stores, processes, transmits, or can affect the security of payment account data. It is designed for internal readiness, first-line control assessment, second-line challenge, and preparation for a formal assessment by a PCI SSC-qualified assessor.

## Contents

1. [`knowledge-base.md`](knowledge-base.md) — concepts, scope, 12 requirements, future-dated requirements, and banking control guidance.
2. [`assessment-method.md`](assessment-method.md) — how to run the assessment, sample, test, rate, report, and close findings.
3. [`assessment-workbook.md`](assessment-workbook.md) — a requirement-level workbook with banking procedures, evidence requests, and assessor prompts.
4. [`evidence-register.md`](evidence-register.md) — evidence index, interview plan, sampling log, and issue records.

## Important use boundary

This is an implementation and readiness aid, not a PCI DSS Report on Compliance (ROC), Attestation of Compliance (AOC), legal opinion, or substitute for the PCI SSC document set. Confirm the applicable version, validation method, reporting instructions, merchant/service-provider obligations, and payment-brand or acquirer requirements before relying on the result. PCI DSS v4.0.1 is the working baseline here; validate current official material at [PCI Security Standards Council](https://www.pcisecuritystandards.org/).

## Suggested implementation sequence

1. Appoint an executive sponsor, PCI programme owner, assessor liaison, and accountable owners for each control domain.
2. Freeze a dated assessment boundary and cardholder data flow. Do not begin with a questionnaire.
3. Establish the Cardholder Data Environment (CDE), connected-to systems, security-impacting systems, people, facilities, providers, and out-of-scope rationale.
4. Populate the evidence register and test the highest-risk requirements first.
5. Record every gap as a defensible issue with risk, root cause, owner, interim treatment, target date, and closure evidence.
6. Produce an executive conclusion that distinguishes assessed, not assessed, not applicable, compensating-control, and unknown populations.

## Banking-specific emphasis

Prioritise ATM and branch networks, card-management platforms, issuer and acquirer processing, payment gateways, HSMs and key management, call centres, mobile and internet banking integrations, cloud and managed service providers, APIs, privileged access, fraud systems, third-party support, data loss prevention, vulnerability management, and resilience or disaster-recovery environments.
