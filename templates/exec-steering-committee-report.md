# Executive Steering Committee Report

**Program:** [Program Name]  
**Report date:** [Date]  
**Reporting period:** [Sprint X / Week X — Date range]  
**Program Manager:** [Name]  
**Executive Sponsor:** [Name]  
**Next steering committee meeting:** [Date, Time]

---

## The only three things this report answers

1. Where are we?
2. What's at risk?
3. What do we need from you?

Everything else is in the appendix.

---

## 1. Overall program status

| | |
|---|---|
| **Overall** | 🟡 Yellow |
| **Schedule** | 🟢 Green |
| **Budget** | 🟢 Green |
| **Compliance / Risk** | 🟡 Yellow |
| **Vendor dependencies** | 🔴 Red |

**Status key:**  
🟢 On track — no action needed  
🟡 At risk — being managed, may need support  
🔴 Off track — action required this week

---

## 2. Where are we — 3 sentences max

> [Write 3 sentences. What phase are we in. What did we complete this period. What are we building toward next period.]

**Example:**
> We completed Sprint 5 and passed compliance gate 2. Core ACH and RTP integrations are built and testing in sandbox. Sprint 6 starts Monday with focus on FedNow integration and full end-to-end testing.

---

## 3. What's at risk

### 🔴 Critical — needs executive action this week

| # | Issue | Impact if unresolved | Ask |
|---|---|---|---|
| 1 | FedNow certification request submitted to [banking partner] 3 weeks ago — no response. | Blocks Sprint 9 certification gate. Pushes go-live by minimum 3 weeks. | Executive sponsor to contact [banking partner] VP relationship directly this week. |

### 🟡 Watch items — being managed, flagged for awareness

| # | Issue | Current mitigation | Escalation trigger |
|---|---|---|---|
| 1 | Engineering bandwidth below plan — 2 engineers on other priorities | Backlog reprioritized; non-critical items deferred | If resource conflict not resolved by [date], will escalate |
| 2 | Penetration test vendor has 2-week backlog | Backup vendor identified and quoted | If primary vendor can't start by [date], switching to backup |

---

## 4. What we need from you

> Use this section deliberately. Every ask should be something only an executive sponsor can unlock — vendor relationships, budget, resource reallocation, cross-team conflict resolution. Do not bring operational decisions to steering committee.

| Ask | From whom | Needed by | Why it can't wait |
|---|---|---|---|
| Direct outreach to [banking partner] on FedNow certification | Executive Sponsor | This week | TPM-level escalation has not moved in 3 weeks |
| [Second ask if applicable] | | | |

---

## 5. Schedule — milestone view

| Milestone | Planned date | Forecast date | Status |
|---|---|---|---|
| Compliance gate 1 — Architecture sign-off | [Date] | [Date] | ✅ Complete |
| Sandbox testing complete | [Date] | [Date] | ✅ Complete |
| Compliance gate 2 — Mid-build sign-off | [Date] | [Date] | ✅ Complete |
| FedNow certification | [Date] | [Date] | 🔴 At risk |
| Compliance gate 3 — Pre-certification sign-off | [Date] | [Date] | 🟡 Dependent on FedNow |
| Go/no-go meeting | [Date] | [Date] | 🟡 Dependent on FedNow |
| Go-live — Phase 1 (canary) | [Date] | [Date] | 🟡 Dependent on FedNow |
| Go-live — Full rollout | [Date] | [Date] | 🟡 Dependent on FedNow |

---

## 6. Budget

| | Budget | Spent to date | Forecast at completion | Variance |
|---|---|---|---|---|
| Engineering | $[X] | $[X] | $[X] | +/- $[X] |
| Compliance / QSA | $[X] | $[X] | $[X] | +/- $[X] |
| Penetration testing | $[X] | $[X] | $[X] | +/- $[X] |
| Vendor / certification fees | $[X] | $[X] | $[X] | +/- $[X] |
| **Total** | **$[X]** | **$[X]** | **$[X]** | **+/- $[X]** |

**Budget notes:**  
[One sentence only. Either "on track" or the specific reason for variance and what you're doing about it.]

---

## 7. Decisions needed from steering committee

> Only include decisions that require executive authority or cross-functional sign-off. Do not include decisions the TPM or PM can make independently.

| # | Decision | Options | Recommendation | Needed by |
|---|---|---|---|---|
| 1 | [Decision topic] | Option A: [description] / Option B: [description] | [Your recommendation and why] | [Date] |

---

## 8. Decisions made since last meeting

| Decision | Who made it | Date | Impact |
|---|---|---|---|
| [Decision] | [Name / Role] | [Date] | [What changes as a result] |

---

## Appendix — for reference only, not discussed in meeting

### Sprint velocity

| Sprint | Planned points | Completed points | Notes |
|---|---|---|---|
| Sprint 1 | | | |
| Sprint 2 | | | |
| Sprint 3 | | | |
| Sprint 4 | | | |
| Sprint 5 | | | |

### Open risk register summary

| Risk ID | Description | Rating | Status |
|---|---|---|---|
| R-8.1 | MFA rollout incomplete for CDE access | Critical | Open |
| P-2 | Engineering bandwidth below plan | High | In progress |
| R-12.3 | Third-party agreements missing PCI DSS clause | High | Open |

*Full risk register: [link to risk-register-pci-dss.md]*

### External dependency tracker

| Dependency | Vendor | Status | Expected date |
|---|---|---|---|
| FedNow enrollment | [Banking partner] | 🔴 Overdue | [Date] |
| Payment processor certification | [Processor] | 🟡 In progress | [Date] |
| QSA assessment | [QSA firm] | 🟢 Confirmed | [Date] |

---

## TPM notes on running steering committee meetings

**Keep it to 30 minutes.** If you need 60 minutes, you have too many items on the agenda or the wrong people in the room.

**Send the report 24 hours in advance.** Executives should arrive having read it. The meeting is for decisions and escalations, not for reading the document aloud.

**The "what do we need from you" section is the whole point.** If you leave a steering committee meeting without a clear decision or executive action, the meeting didn't need to happen.

**Never surprise the exec sponsor.** If something is going to be 🔴 in the meeting, they should know before they walk in. A steering committee is not where you deliver bad news for the first time.

**Own the status colors.** Don't mark everything green to avoid difficult conversations. A 🟡 that becomes 🔴 two weeks later is a TPM credibility problem. Call it yellow when it's yellow.

---

*Template version 1.0 — fintech-tpm-playbook*
