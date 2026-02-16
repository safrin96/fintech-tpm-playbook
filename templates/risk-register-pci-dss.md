# Risk Register — PCI DSS v4.0.1 Compliance Program

**Program:** [Program Name]  
**Standard:** PCI DSS v4.0.1 (active as of Q4 2024; March 2025 phased requirements now mandatory)  
**Last updated:** [Date]  
**Program Manager:** [Name]  
**Compliance Owner:** [Name]  
**QSA / Assessor:** [Firm Name, if engaged]

---

## How to use this register

Review weekly during active compliance sprints. Review bi-weekly during steady state. Each risk owner is responsible for updating their row before every steering committee meeting.

**Likelihood:** 1 (Low) — 5 (High)  
**Impact:** 1 (Low) — 5 (High)  
**Risk Score:** Likelihood × Impact  

| Score range | Rating |
|---|---|
| 1–4 | Low |
| 5–9 | Medium |
| 10–16 | High |
| 20–25 | Critical |

---

## Active Risks

### Requirement 1 — Network Security Controls

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| R-1.1 | Firewall rules not reviewed in 6+ months — CDE exposure unvalidated | 3 | 5 | 15 | High | Security | Schedule quarterly review; automate rule change alerts | Open | [Date] |
| R-1.2 | Network segmentation between CDE and non-CDE systems incomplete | 2 | 5 | 10 | High | Engineering | Complete VLAN segmentation; validate with penetration test | In Progress | [Date] |
| R-1.3 | Third-party vendor network access not restricted to least privilege | 3 | 4 | 12 | High | Security | Audit all vendor access; implement time-limited access tokens | Open | [Date] |

---

### Requirement 2 — Secure Configurations

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| R-2.1 | Default credentials in use on payment-adjacent systems | 2 | 5 | 10 | High | Engineering | Automated credential scan in CI/CD pipeline | Open | [Date] |
| R-2.2 | System hardening standards not documented for new CDE components | 3 | 3 | 9 | Medium | Security | Create and publish hardening baseline; add to onboarding | In Progress | [Date] |

---

### Requirement 3 — Protect Account Data

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| R-3.1 | PAN data stored beyond authorized retention period | 2 | 5 | 10 | High | Engineering | Automated data purge job; retention policy enforcement | Open | [Date] |
| R-3.2 | Cardholder data discovered outside defined CDE boundary | 2 | 5 | 10 | High | Compliance | Data discovery scan across all environments; scope remediation | Open | [Date] |
| R-3.3 | Encryption key management process undocumented | 3 | 4 | 12 | High | Security | Document key rotation schedule; assign custodians | In Progress | [Date] |

---

### Requirement 4 — Protect Cardholder Data in Transit

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| R-4.1 | TLS version below 1.2 on payment endpoints | 2 | 5 | 10 | High | Engineering | Deprecate TLS 1.0/1.1; enforce TLS 1.2+ across all endpoints | Open | [Date] |
| R-4.2 | Certificate expiry monitoring not automated | 3 | 4 | 12 | High | Engineering | Implement cert expiry alerting (90/30/7 day thresholds) | Open | [Date] |

---

### Requirement 6 — Secure Software Development

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| R-6.1 | No formal code review process for payment-related changes | 3 | 4 | 12 | High | Engineering | Require 2-person review for all CDE-touching PRs | In Progress | [Date] |
| R-6.2 | Third-party libraries in payment flow not inventoried | 3 | 4 | 12 | High | Engineering | Generate SBOM (software bill of materials); schedule review | Open | [Date] |
| R-6.3 | Web-skimming protection not implemented on payment pages (v4.0.1 requirement) | 3 | 5 | 15 | High | Engineering | Implement script inventory and CSP headers on all checkout pages | Open | [Date] |

> **Note:** R-6.3 is a new mandatory requirement in PCI DSS v4.0.1. All scripts loading on payment pages must be authorized and integrity-checked. This was a best practice in v3.x; it is now a hard requirement. If you have third-party analytics, chat widgets, or A/B testing scripts on checkout pages, this is likely an open finding.

---

### Requirement 7 — Restrict Access to System Components

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| R-7.1 | Access to CDE not restricted to least privilege | 3 | 4 | 12 | High | Security | Access review; role-based permissions audit | Open | [Date] |
| R-7.2 | Privileged access not reviewed on quarterly cadence | 3 | 3 | 9 | Medium | Security | Establish quarterly access review; automate off-boarding triggers | Open | [Date] |

---

### Requirement 8 — Identify Users and Authenticate Access

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| R-8.1 | MFA not enforced for all CDE access (v4.0.1 mandatory) | 3 | 5 | 15 | **Critical** | Security | Complete MFA rollout; block non-MFA access to CDE | **Open** | [Date] |
| R-8.2 | Shared/generic credentials in use for system accounts | 2 | 4 | 8 | Medium | Engineering | Assign individual service accounts; audit shared credential use | In Progress | [Date] |
| R-8.3 | Password policy not meeting v4.0.1 minimums (12 chars, complexity) | 2 | 3 | 6 | Medium | Security | Update policy; force reset on next login | Open | [Date] |

> **Note:** R-8.1 is your highest priority open risk. MFA for all CDE access is no longer optional under v4.0.1. If a QSA finds this open, it is an automatic finding that blocks certification.

---

### Requirement 10 — Log and Monitor All Access

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| R-10.1 | Audit logs not capturing all required CDE events | 3 | 4 | 12 | High | Engineering | Audit log coverage review; add missing event types | Open | [Date] |
| R-10.2 | Log retention below 12-month minimum | 2 | 4 | 8 | Medium | Engineering | Extend log retention policy; archive to cold storage | Open | [Date] |
| R-10.3 | Log tampering protection not implemented | 2 | 5 | 10 | High | Security | Implement write-once log storage; integrity monitoring | Open | [Date] |

---

### Requirement 11 — Test Security Regularly

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| R-11.1 | Annual penetration test not completed or overdue | 2 | 5 | 10 | High | Security | Schedule pen test; engage approved vendor | Open | [Date] |
| R-11.2 | Vulnerability scanning not running on CDE systems | 3 | 4 | 12 | High | Security | Deploy ASV-approved scanner; establish scan cadence | Open | [Date] |
| R-11.3 | No intrusion detection on CDE network segments | 3 | 4 | 12 | High | Security | Deploy IDS/IPS on CDE; configure alerting thresholds | In Progress | [Date] |

---

### Requirement 12 — Organizational Policies and Programs

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| R-12.1 | Information security policy not reviewed in 12 months | 2 | 3 | 6 | Medium | Compliance | Annual review scheduled; assign policy owner | Open | [Date] |
| R-12.2 | Incident response plan not tested | 3 | 4 | 12 | High | Compliance | Tabletop exercise scheduled; update plan post-exercise | Open | [Date] |
| R-12.3 | Third-party service provider agreements don't include PCI DSS obligations | 3 | 5 | 15 | High | Legal | Contract review; update MSAs to include PCI DSS acknowledgment | Open | [Date] |

---

## Program-Level Risks (not tied to a specific PCI requirement)

| ID | Risk Description | Likelihood | Impact | Score | Rating | Owner | Mitigation | Status | Target Date |
|---|---|---|---|---|---|---|---|---|---|
| P-1 | QSA engagement delayed — assessment timeline at risk | 2 | 4 | 8 | Medium | TPM | Confirm QSA start date; identify backup assessor | Open | [Date] |
| P-2 | Engineering bandwidth insufficient for compliance sprint work | 3 | 4 | 12 | High | TPM | Escalate to executive sponsor; propose resource reallocation | Open | [Date] |
| P-3 | Scope creep — new product features expanding CDE boundary mid-program | 3 | 5 | 15 | High | TPM | Freeze CDE scope during assessment period; require change control | Open | [Date] |
| P-4 | Key compliance stakeholder departure mid-program | 1 | 5 | 5 | Medium | TPM | Document all decisions; ensure knowledge transfer plan | Open | [Date] |

---

## Closed Risks

| ID | Risk Description | Closed Date | Resolution |
|---|---|---|---|
| | | | |

---

## Risk register governance

**Review cadence:** Weekly during active remediation sprints. Bi-weekly in steady state.  
**Escalation threshold:** Any risk rated High or Critical that has not moved in two review cycles escalates to the executive steering committee.  
**Change control:** Any change to CDE scope, system components, or implementation approach requires a risk register update before implementation begins.

---

## TPM notes on running this register

The most common mistake on PCI DSS programs is treating the risk register as a compliance artifact rather than a program management tool. It should be the first thing open at every sprint review. Engineering should be able to see their rows. Compliance should own their A column. The TPM should be tracking velocity: are we closing risks faster than new ones are opening?

If you have more than 3 Critical or High risks sitting Open for more than two sprint cycles, you have a resourcing problem, not a compliance problem. Escalate it that way.

---

*Template version 1.0 — fintech-tpm-playbook*  
*Mapped to PCI DSS v4.0.1 — active standard as of Q4 2024*
