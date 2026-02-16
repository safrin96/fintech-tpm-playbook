# fintech-tpm-playbook

A practical reference library for Technical Program Managers working in payments, financial infrastructure, and regulated fintech environments.

Built from real program delivery experience across ERP transformations, cloud analytics, and enterprise financial systems. Every template here reflects how programs actually run — not how textbooks say they should.

---

## What's in here

| File | What it is |
|---|---|
| [`templates/raci-payments-platform-launch.md`](templates/raci-payments-platform-launch.md) | RACI matrix for a full payments platform launch covering engineering, product, compliance, legal, and ops |
| [`templates/risk-register-pci-dss.md`](templates/risk-register-pci-dss.md) | Risk register template scoped to PCI DSS v4.0.1 compliance programs |
| [`templates/sprint-cadence-payment-rails.md`](templates/sprint-cadence-payment-rails.md) | Sprint cadence doc for a payment rails integration (ACH, RTP, FedNow) |
| [`templates/exec-steering-committee-report.md`](templates/exec-steering-committee-report.md) | Executive steering committee reporting template for payment platform programs |
| [`guides/setup-guide.md`](guides/setup-guide.md) | Step-by-step guide to using and adapting these templates |

---

## Who this is for

- TPMs targeting fintech companies (Stripe, Ramp, Brex, Chime, Block, PayPal, Affirm, Mercury, Intuit)
- Program managers moving from enterprise or SaaS into financial services
- Anyone running a program that touches payment processing, compliance, or financial infrastructure

---

## Why these four templates

These are the artifacts that come up most in fintech TPM interviews and day-to-day work:

**RACI** — Payments launches involve more stakeholders than almost any other product category. Engineering, product, compliance, legal, security, finance ops, customer support, and external vendors all have a seat. Without a clear accountability map, the program falls apart at the handoff points.

**Risk register** — PCI DSS v4.0.1 became the only active standard in 2024. The phased requirements deadline passed March 2025. A risk register scoped to this standard tells interviewers you understand that compliance is a program management problem, not just a security team problem.

**Sprint cadence** — Payment rails integrations (ACH, RTP, FedNow) have external dependencies that most sprint frameworks don't account for: bank certification timelines, sandbox vs production environment gaps, and regulatory approval gates. This template builds those in from the start.

**Exec steering report** — C-suite stakeholders at fintech companies want three things: where are we, what's at risk, and what do you need from me. This template is structured around those three questions and nothing else.

---

## How to use these

Clone the repo and copy whichever template fits your program. Every template has inline comments (marked `<!-- note: -->`) explaining why each section exists and what to customize.

```bash
git clone https://github.com/YOUR_USERNAME/fintech-tpm-playbook.git
```

These are Markdown files. They render cleanly on GitHub, paste into Notion or Confluence, and convert to PDF or DOCX without reformatting.

---

## Context

Built by a CSPO certified Technical Program Manager with experience delivering:
- $1.3M ERP transformation for a financial services client (Dynamics 365, 300+ users, 95% adoption)
- Enterprise analytics modernization supporting $30M+ in financial reporting and planning operations
- Cloud cost governance (FinOps) for enterprise SaaS customers at scale
- GDPR/CCPA-aligned data governance across analytics pipelines

---

## Contributing

If you've run payments or compliance programs and have templates that don't exist here, PRs are welcome. The goal is a living resource, not a static document.

---

*Last updated: February 2026*
