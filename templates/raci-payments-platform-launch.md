# RACI Matrix — Payments Platform Launch

**Program:** [Payments Platform Name]  
**Version:** 1.0  
**Last updated:** [Date]  
**Program Manager:** [Name]

---

## How to read this

| Symbol | Meaning |
|---|---|
| **R** | Responsible — does the work |
| **A** | Accountable — owns the outcome, signs off |
| **C** | Consulted — input required before decision |
| **I** | Informed — notified of decisions/progress |

> One **A** per row. If you have two, you have a gap.  
> If a cell is blank, that team has no role in this activity.

---

## Roles key

| Abbreviation | Role |
|---|---|
| TPM | Technical Program Manager |
| ENG | Engineering (payments/backend) |
| FE | Frontend Engineering |
| PM | Product Manager |
| SEC | Security |
| COMP | Compliance |
| LEGAL | Legal |
| FIN | Finance / Finance Ops |
| OPS | Operations / Launch Ops |
| CS | Customer Support |
| VENDOR | External payment processor / banking partner |
| EXEC | Executive Sponsor |

---

## Phase 1: Discovery & Requirements

| Activity | TPM | ENG | PM | SEC | COMP | LEGAL | FIN | OPS | VENDOR | EXEC |
|---|---|---|---|---|---|---|---|---|---|---|
| Define program scope and success metrics | A | C | R | I | C | I | C | I | | I |
| Payment rails selection (ACH / RTP / FedNow / card) | C | R | A | I | C | C | C | | C | I |
| PCI DSS scoping — define cardholder data environment (CDE) | C | R | I | A | R | I | I | | C | |
| Legal review — payment facilitator vs ISO model | I | | C | | C | A | C | | | I |
| Vendor / processor contract review | I | | I | | C | A | I | R | C | I |
| Fraud and risk appetite definition | C | C | R | C | A | C | R | | C | I |
| Executive program kickoff | R | I | I | I | I | I | I | I | | A |

---

## Phase 2: Architecture & Design

| Activity | TPM | ENG | PM | SEC | COMP | LEGAL | FIN | OPS | VENDOR | EXEC |
|---|---|---|---|---|---|---|---|---|---|---|
| Payment architecture design (APIs, message flows) | C | A | C | C | I | | | | C | |
| Tokenization and encryption design | I | R | | A | C | | | | C | |
| Idempotency and retry logic design | C | A | I | C | | | | | I | |
| Fraud detection integration design | C | R | C | A | C | | C | | C | |
| Sandbox / test environment setup | R | A | I | C | I | | | | R | |
| Compliance gate checklist (pre-build) | A | C | C | C | R | C | | | | |
| Data residency and privacy review | C | C | C | R | A | C | | | | |

---

## Phase 3: Build & Integration

| Activity | TPM | ENG | FE | PM | SEC | COMP | VENDOR | OPS |
|---|---|---|---|---|---|---|---|---|
| Payment API integration (core rails) | I | A | | | C | | R | |
| Frontend payment UI build | I | C | A | R | C | | | |
| Webhook implementation and event handling | C | A | | I | | | R | |
| 3DS authentication integration | C | R | R | I | A | | C | |
| Dependency tracking — vendor certifications | A | I | | I | | C | R | I |
| Sprint review and demo coordination | A | R | R | R | I | I | I | I |
| Compliance milestone gate (mid-build) | A | C | | C | R | R | | |
| Staging environment validation | R | A | A | I | C | | R | |

---

## Phase 4: Testing & Certification

| Activity | TPM | ENG | PM | SEC | COMP | LEGAL | VENDOR | OPS | CS |
|---|---|---|---|---|---|---|---|---|---|
| QA test plan sign-off | A | R | C | C | C | | | | |
| Penetration testing | C | R | | A | C | | | | |
| PCI DSS QSA assessment coordination | A | C | | C | R | C | C | | |
| Payment processor certification | R | R | | | C | | A | | |
| FedNow / RTP network certification (if applicable) | R | R | | | C | C | A | | |
| Fraud and dispute workflow testing | C | R | C | | C | | C | A | R |
| Load testing — payment throughput | C | A | | I | | | | | |
| Legal sign-off — terms of service, payment disclosures | I | | I | | C | A | | | |

---

## Phase 5: Launch Readiness

| Activity | TPM | ENG | PM | SEC | COMP | LEGAL | FIN | OPS | CS | EXEC |
|---|---|---|---|---|---|---|---|---|---|---|
| Go/no-go criteria definition | A | C | C | C | C | C | C | C | C | I |
| Go/no-go meeting | R | I | I | I | I | I | I | I | I | A |
| Runbook and rollback plan sign-off | A | R | I | C | | | | R | | |
| Customer support training and readiness | R | | C | | | | | A | R | |
| Monitoring and alerting setup | C | A | | R | | | | | | |
| Phased rollout plan (% traffic) | A | R | R | | | | | C | | I |
| Executive launch communication | R | | I | | I | I | I | I | I | A |

---

## Phase 6: Post-Launch & Steady State

| Activity | TPM | ENG | PM | SEC | COMP | FIN | OPS | CS |
|---|---|---|---|---|---|---|---|---|
| Payment success rate monitoring (first 30 days) | A | R | I | | | | | |
| Incident response — payment failures | C | A | I | C | | | R | R |
| Chargeback and dispute rate review | I | | R | | C | A | A | R |
| 30-day post-launch retrospective | A | R | R | R | | | R | R |
| Compliance evidence collection for audit | R | C | | C | A | | | |
| Vendor performance review | A | C | I | | C | C | | |

---

## Common RACI failure points in payments programs

**Compliance gate ownership** — if COMP is only "Consulted" on architecture decisions, you will find compliance gaps in QA. Move COMP to "Accountable" on all CDE-touching design decisions.

**Vendor certification timelines** — external payment processors and banking partners operate on their own timelines. TPM should be "Accountable" for tracking those dependencies, not Engineering.

**Fraud and risk appetite** — this is frequently unowned. Someone in Compliance or Risk needs an "A" here before architecture starts, or you will redesign fraud controls twice.

**Go/no-go** — the executive sponsor should be "Accountable" for the go/no-go decision, not the TPM. TPM runs the meeting and owns the criteria. Exec owns the call.

---

*Template version 1.0 — fintech-tpm-playbook*
