# Project Context Document

**Project:** SAMI Phase 2 — AI-Assisted Alert Triage on SonicWall Unified Manager Dashboard  
**Date:** 2026-06-20  
**Source:** EPIC_UM-MSW_SAMI-Alert-Triage.md, CLAUDE.md, sami-page1-dashboard-uuif.html, live dashboard screenshots, and user conversation  
**Version:** 1.0

---

## 1. Problem Statement

MSP partners managing 25–75+ tenants on the SonicWall Unified Manager face high daily alert volumes — device notifications, CVE vulnerabilities, behavioral anomalies, and policy gaps — with no intelligent prioritization to separate critical threats from low-signal noise. The result is a growing backlog of untriaged alerts that increases mean time-to-respond and places unnecessary operational burden on MSP staff.

---

## 2. ICP (Ideal Customer Profile)

Mid-size MSP partners managing between 25 and 75 SonicWall tenants via the Unified Manager (UM) platform. They operate in-house security operations without dedicated threat-hunting staff. They rely on UM's Notifications dashboard daily but are overwhelmed by undifferentiated alert volume across multiple tenants and product categories (Firewalls, Access Points, Switches, Capture Client, Capture Client MDR). They currently have no AI-assisted prioritization and must manually review every notification to determine criticality.

---

## 3. Pain Points

- **Alert volume overload:** No intelligent ranking — every notification appears at equal weight regardless of actual threat severity
- **No cross-tenant prioritization:** Alerts are not aggregated or ranked across tenants; partners must switch context per tenant to assess impact
- **Missing alert categories:** Behavioral anomalies, CVE vulnerabilities, and policy gaps are not currently surfaced alongside device notifications — they must be found separately
- **No AI assistance:** SAMI AI is not yet surfaced on the dashboard; partners cannot benefit from automated triage recommendations
- **High mean time-to-respond:** Manual review of every alert creates a growing untriaged backlog and delays response to real threats

---

## 4. Proposed Solution

Add a **SAMI Alerts tab** alongside the existing Notifications tab on the UM Dashboard. The SAMI tab contains two sections:

**Section 1 — Device Alert Triage**
- Surfaces existing device notification alerts (Firewalls, Access Points, Switches, etc.) re-ranked by SAMI AI confidence score
- Separates Critical alerts from non-critical alerts
- Shows SAMI recommended action per alert (Acknowledge / Escalate / Dismiss)
- Supports bulk triage for MSP role

**Section 2 — AI Insight Alerts**
- Surfaces three new alert categories: Behavioral Anomalies, Policy Gaps, CVE Vulnerabilities
- Each category shows Critical alerts first, followed by non-critical alerts
- Each alert carries a SAMI confidence score and recommended action
- Alerts below confidence threshold render without AI chip but remain available for manual triage

**Supporting behaviors:**
- Untriaged count badge on the SAMI tab
- Real-time badge decrement after each triage action
- Graceful degradation when SAMI service is unavailable (manual triage only, no error blocking alerts)
- Feature-flag controlled: MSP role only; hidden when flag is off

---

## 5. Success Metrics

Per the EPIC (targets to be baselined before launch):

- **Untriaged alert reduction** — reduction in untriaged alert count vs. pre-launch baseline (target TBD)
- **Mean time-to-triage** — reduction in average time from alert appearance to triage action taken (target TBD)
- **SAMI recommendation acceptance rate** — percentage of triage actions that match SAMI's recommendation (target TBD)
- **Partner engagement** — click-through rate and session frequency on the SAMI triage panel, measured via Pendo

---

## 6. Design Constraints

**Platform:** Web, desktop-first (SonicWall Unified Manager — browser-based)  
**Geography:** Not defined in source material  
**Accessibility:** Not defined in source material  
**Technical:**
- Design system: UUIF 9.2 — all components must use `var(--uuif-*)` CSS tokens; `Nunito Sans` font; semantic class names (`uuif-btn`, `uuif-chip`, `uuif-card`, etc.)
- Fixed three-panel chrome: Nav Rail 60 px + SubNav 266 px + Top Bar 46 px — widths are non-negotiable
- Feature-flag controlled: panel hidden when flag is disabled; no broken or empty container shown
- Cross-tenant alert queries must be enforced at the API level, not only in the UI
- Panel must paginate or virtualize when untriaged count exceeds a defined threshold (TBD)

**Other:**
- SAMI AI callout pattern (orange left border on `--uuif-fill-orange-lighter` background) is the established visual convention for AI-generated content — treat as standard
- Concurrent triage conflict resolution strategy is undefined — must be resolved before engineering handoff

---

## 7. Open Questions

1. What is the SAMI confidence score threshold below which the AI chip is suppressed? (PM + data science alignment required)
2. What is the escalation target system when a user selects "Escalate"? (TBD — must be defined before handoff)
3. Should Enterprise IT Admins see the SAMI tab at all, or is it strictly MSP-only? (marked TBD in EPIC)
4. What is the maximum render limit for the triage panel before pagination/virtualization is required?
5. What is the conflict resolution strategy for concurrent triage (last-write-wins vs. optimistic lock)?
6. Should the three AI Insight alert categories (Behavioral Anomalies, Policy Gaps, CVE Vulnerabilities) each have their own sub-tab, or appear as grouped sections within a single view?
7. Does the SAMI tab replace or sit alongside the existing Notifications tab? (Current intent: alongside, as a separate tab)
8. Should MSPs be able to filter or sort alerts within each section, or is SAMI confidence score the only ordering mechanism?

---

## 8. Gaps

1. **Baseline metrics** — Success metric targets are all TBD. Baseline alert volume and mean triage time data must be collected pre-launch before launch criteria can be set.
2. **SAMI confidence threshold** — Not defined. Affects which alerts display an AI chip and which go to manual triage. Requires PM and data science alignment.
3. **Escalation workflow destination** — Post-action escalation target (system or team) is undefined. Epic cannot be marked done without this.
4. **Concurrent triage conflict resolution** — No strategy defined. Must be decided before engineering picks this up.
5. **Bulk triage partial failure handling** — Behavior on partial failure during a bulk action is not fully specified. Required before QA.
6. **Accessibility requirements** — No WCAG or accessibility target stated. Recommend defining a minimum standard (WCAG 2.1 AA is typical for enterprise).
7. **Geography and compliance** — No regional launch target or data residency / compliance requirements stated.
8. **User research** — No evidence of MSP partner interviews or usability testing data in source material. Recommend 5–10 partner interviews before finalizing the triage UX pattern.
9. **Pagination threshold** — Maximum untriaged alert count before virtualization is required is TBD. Engineering needs this to scope the implementation.

---

*Generated by project-context skill. Update this document as decisions are made and open questions are resolved.*
