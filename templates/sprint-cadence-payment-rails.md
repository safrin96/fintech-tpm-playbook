# Sprint Cadence — Payment Rails Integration

**Program:** [Program Name]  
**Rails in scope:** ACH · RTP · FedNow · [remove any not applicable]  
**Sprint length:** 2 weeks  
**Program start date:** [Date]  
**Target go-live:** [Date]  
**Program Manager:** [Name]

---

## Why payment rails integrations need their own cadence doc

Standard sprint frameworks assume your dependencies are internal. Payment rails integrations don't work that way.

External dependencies specific to payments programs:
- Bank / processor sandbox access (often takes 2–4 weeks to provision)
- Network certification (FedNow, RTP Clearing House) runs on the network's timeline, not yours
- Nacha rule compliance review for ACH programs
- Banking partner API change windows (usually monthly)
- Regulatory approval gates for certain payment types

If you run a standard sprint cadence without accounting for these, you will hit a certification dependency in sprint 6 that you could have started in sprint 1.

---

## Program phases and sprint map

### Phase 0: Pre-Sprint Setup (Weeks -4 to 0)

These tasks must be complete before sprint 1 starts. They take longer than engineers expect.

| Task | Owner | Duration | Notes |
|---|---|---|---|
| Request sandbox credentials from payment processor | TPM | 2–4 weeks | Do this on day 1 of program kickoff |
| Request FedNow participant enrollment (if in scope) | TPM + Compliance | 4–6 weeks | FedNow enrollment is through your banking partner, not the Fed directly |
| Request RTP network access via Clearing House | TPM + Engineering | 2–3 weeks | Requires a Clearing House participant sponsor |
| Define cardholder data environment (CDE) scope | TPM + Security + Compliance | 1 week | Required before any architecture design begins |
| Confirm QSA engagement if PCI assessment is in scope | TPM + Compliance | 1–2 weeks | |
| Legal review of payment facilitator / processor agreement | Legal | 1–2 weeks | Start concurrently with sandbox request |
| Align on fraud and risk thresholds | PM + Risk + Compliance | 1 week | Decisions needed before architecture sprint |

> **TPM note:** Sandbox provisioning and FedNow enrollment have the longest external lead times. Missing these in Phase 0 typically delays the program by 3–5 weeks. Treat them as the first items on your program plan, not afterthoughts.

---

### Phase 1: Architecture & Design (Sprints 1–2)

**Sprint 1 goals:**
- Payment API architecture finalized (endpoints, message formats, error handling)
- Idempotency and retry strategy documented and agreed
- Data flow diagram showing CDE boundary
- Tokenization approach confirmed with security

**Sprint 2 goals:**
- Webhook design and event schema finalized
- 3DS authentication flow designed (if card payments in scope)
- Fraud detection integration points mapped
- Compliance gate 1 completed (architecture sign-off)

**Recurring ceremonies:**

| Ceremony | Cadence | Duration | Who |
|---|---|---|---|
| Sprint planning | Start of each sprint | 2 hours | TPM, Engineering, PM |
| Daily standup | Daily | 15 min | Engineering leads |
| Architecture review | Weekly (Sprints 1–2) | 1 hour | TPM, Engineering, Security, Compliance |
| Dependency check | Weekly | 30 min | TPM only — track external vendor/network status |
| Sprint review | End of each sprint | 1 hour | TPM, Engineering, PM, stakeholders |
| Retrospective | End of each sprint | 45 min | TPM, Engineering |

**Compliance gate 1 — Architecture sign-off**  
Required before Sprint 3 begins.

| Checkpoint | Owner | Pass criteria |
|---|---|---|
| CDE scope document reviewed and approved | Security + Compliance | Signed-off data flow diagram |
| Encryption and tokenization approach approved | Security | Written approval on record |
| Third-party script inventory for payment pages | Security | All scripts listed; none unauthorized |
| Legal review of payment processor terms | Legal | Signed-off |

---

### Phase 2: Core Build (Sprints 3–6)

**Sprint 3 goals:**
- ACH integration: initiate, retrieve, cancel endpoints built and unit tested
- Webhook handler implemented
- Sandbox environment functional for internal testing

**Sprint 4 goals:**
- RTP integration (if in scope): initiate and status endpoints
- Error handling and retry logic implemented
- Internal end-to-end test in sandbox passing

**Sprint 5 goals:**
- FedNow integration (if in scope): initiate and reconciliation endpoints
- Fraud detection integrated and threshold logic tested
- Compliance gate 2 completed (mid-build sign-off)

**Sprint 6 goals:**
- Full payment flow working end-to-end in sandbox
- Monitoring and alerting configured
- Runbook first draft complete

**Compliance gate 2 — Mid-build sign-off**  
Complete at end of Sprint 5.

| Checkpoint | Owner | Pass criteria |
|---|---|---|
| MFA enforced for all CDE access | Security | No exceptions |
| Access control review — CDE systems | Security | Least privilege confirmed |
| Audit logging coverage — all CDE events captured | Engineering | Log coverage report reviewed |
| Dependency status — all external certifications on track | TPM | No critical path delays |

---

### Phase 3: Testing & Certification (Sprints 7–9)

This phase has the most external dependencies. Start certification requests in Sprint 5, not Sprint 7.

**Sprint 7 goals:**
- QA test plan executed — all payment flows
- Penetration test initiated (allow 2–3 weeks for results)
- Payment processor certification request submitted (if required)

**Sprint 8 goals:**
- Penetration test findings remediated
- FedNow / RTP network certification in progress
- Load testing completed — define target TPS and confirm system handles it
- Compliance gate 3 completed (pre-certification sign-off)

**Sprint 9 goals:**
- All certifications received
- External security scan (ASV) completed and passing
- Go/no-go criteria finalized

**Compliance gate 3 — Pre-certification sign-off**  
Complete at end of Sprint 8. This gate must be passed before go/no-go meeting is scheduled.

| Checkpoint | Owner | Pass criteria |
|---|---|---|
| Penetration test — no critical or high findings open | Security | Written remediation confirmation |
| PCI DSS evidence package assembled | Compliance | All required artifacts ready for QSA |
| Payment processor certification confirmed | TPM + Vendor | Written confirmation from processor |
| FedNow / RTP certification confirmed (if in scope) | TPM + Vendor | Written confirmation from network |
| Fraud thresholds validated in load testing | PM + Engineering | Thresholds hold under peak load |

---

### Phase 4: Launch (Sprint 10)

**Sprint 10 goals:**
- Go/no-go meeting held and documented
- Phased rollout plan agreed (% traffic, rollback triggers)
- Customer support trained and signed off
- Monitoring dashboard live

**Go/no-go criteria — must all be green before scheduling meeting:**

| Criteria | Owner | Status |
|---|---|---|
| All compliance gates passed | Compliance | |
| All certifications received | TPM | |
| Zero Critical / High open security findings | Security | |
| Rollback plan tested and documented | Engineering | |
| Customer support training complete | Ops | |
| Executive sponsor approval | Exec | |

**Phased rollout recommendation:**

| Phase | Traffic % | Duration | Rollback trigger |
|---|---|---|---|
| Canary | 1–5% | 48 hours | Any payment failure rate above [X]% |
| Limited | 10–20% | 3–5 days | Any payment failure rate above [X]% |
| Broad | 50% | 3–5 days | Any payment failure rate above [X]% |
| Full | 100% | Ongoing | Standard incident response thresholds |

---

### Phase 5: Post-Launch Monitoring (Weeks 1–4 post go-live)

| Activity | Cadence | Owner |
|---|---|---|
| Payment success rate review | Daily (week 1), then weekly | TPM + Engineering |
| Fraud rate review | Daily (week 1), then weekly | PM + Risk |
| Incident response readiness check | Daily (week 1) | TPM + Ops |
| 30-day retrospective | End of week 4 | TPM |
| Compliance evidence collection | Ongoing | Compliance |
| Vendor performance review | Monthly | TPM |

---

## External dependency tracker

Keep this updated weekly. Any item that slips here moves the program end date.

| Dependency | Vendor / Network | Date requested | Expected completion | Actual completion | Status |
|---|---|---|---|---|---|
| Sandbox credentials | [Processor name] | | | | |
| FedNow enrollment | [Banking partner] | | | | |
| RTP network access | Clearing House | | | | |
| Payment processor certification | [Processor name] | | | | |
| ASV security scan | [ASV name] | | | | |
| Penetration test | [Vendor name] | | | | |
| QSA assessment | [QSA firm] | | | | |

---

## Common failure modes in payment rails programs

**Starting certifications too late.** FedNow enrollment and RTP access requests take 4–6 weeks. If you request them in sprint 6, they will not be complete before your sprint 9 certification gate.

**Treating compliance gates as checkboxes.** Each compliance gate is a hard stop. Engineering should not begin the next phase until gate sign-off is documented. Undocumented verbal approvals are not approvals.

**Underscoping the fraud review.** Fraud threshold decisions affect architecture. If fraud and risk appetite aren't locked in Phase 0, you will revisit the architecture in Sprint 4.

**Missing the monitoring setup.** Payment monitoring is not a post-launch task. Dashboards and alerting should be live before go/no-go, not after.

---

*Template version 1.0 — fintech-tpm-playbook*
