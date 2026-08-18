# UM-MSW | SAMI AI-Assisted Alert Triage on UM Dashboard

**Epic Name:** `UM-MSW | SAMI AI-Assisted Alert Triage on UM Dashboard`
**Owner:** TBD (PM) — UM / MSW
**Jira Project:** UM
**Format:** Conditional Logic

---

## Description

**User Story:** As an MSP partner managing multiple tenants, I want AI-powered alert triage recommendations surfaced on the UM dashboard so that I can prioritize and act on critical alerts faster without manually reviewing every notification.

**Problem Statement:** MSP partners managing 25–75+ tenants face high daily alert volumes with no intelligent prioritization to separate critical threats from low-signal noise. The result is a growing backlog of untriaged alerts that increases mean time-to-respond and places unnecessary operational burden on MSP staff.

**Business Value:** Reducing untriaged alert volume via SAMI-driven recommendations directly improves partner operational efficiency, decreases threat response latency, and reinforces SonicWall's AI-first management platform positioning.

**Success Metrics**
- Reduction in untriaged alert count — target TBD (baseline measurement required pre-launch)
- Mean time-to-triage per alert — target TBD
- SAMI recommendation acceptance rate — target TBD
- Partner engagement with SAMI triage panel — measured via Pendo (click-through, session frequency)

---

## Acceptance Criteria

### Role-Based Behavior

| Behavior | MSP Partner | Enterprise IT Admin |
|---|---|---|
| SAMI triage panel visible on Dashboard | Yes | TBD |
| AI recommendation chip shown per alert | Yes | TBD |
| Bulk triage action available | Yes | No |
| Cross-tenant alert aggregation | Yes | No |
| Untriaged count badge displayed | Yes | TBD |

---

### Display Logic

Ordered by priority:

1. SAMI triage panel renders on UM Dashboard — condition: user role = MSP AND feature flag enabled
2. Alerts sorted by SAMI confidence score descending (High → Medium → Low)
3. Untriaged alert count badge visible — condition: untriaged count > 0
4. Empty state rendered — condition: untriaged count = 0; display confirmation message
5. SAMI recommendation chip shown per alert — condition: AI confidence score ≥ TBD threshold
6. Alerts below confidence threshold render without chip — manual triage option remains available

---

### Suppression Rules

| Condition | Applies To | Behavior |
|---|---|---|
| Alert already triaged by any user | Individual alert | Remove from untriaged queue; do not re-surface |
| SAMI confidence score below threshold | Individual alert | Suppress AI chip; keep alert in queue for manual triage |
| Tenant deactivated or suspended | All alerts from that tenant | Suppress from triage panel entirely |
| Feature flag disabled | All users | SAMI triage panel hidden; no degraded state shown |

---

### Data Capture

| Field | Type | Notes |
|---|---|---|
| Alert ID | String | Unique per alert, cross-tenant scoped |
| SAMI confidence score | Float | Range: 0.0–1.0 |
| SAMI recommended action | Enum | Acknowledge / Escalate / Dismiss — TBD final set |
| Triage action taken | Enum | Must match SAMI action enum |
| Triage actor | String | User ID |
| Triage timestamp | DateTime | UTC |
| SAMI recommendation accepted | Boolean | True if user action matches SAMI recommendation |
| Tenant ID | String | Required for cross-tenant scoping and audit |

---

### Post-Action Workflow

1. User selects triage action (Acknowledge / Escalate / Dismiss)
   - a. Alert is removed from untriaged queue immediately
   - b. Triage event logged: actor, timestamp, action taken, tenant ID
   - c. If action = Escalate → escalation workflow triggered (target system TBD — define before handoff)
2. SAMI acceptance recorded — if user action matches SAMI recommendation, flag `recommendation_accepted = true`
3. Untriaged badge count decrements in real-time after each action
4. Bulk triage (MSP only): all selected alerts processed sequentially; partial failure must not leave queue in inconsistent state

---

### Feature Flag

- [ ] Backend flag controls SAMI triage panel visibility — toggleable without code deploy.

---

### Edge Cases & Engineering Notes

**High alert volume:** Triage panel must paginate or virtualize rendering if untriaged count exceeds TBD threshold — define render limit before implementation.

**Concurrent triage:** If two users triage the same alert simultaneously, define conflict resolution strategy (last-write-wins or optimistic lock) — do not leave alert in ambiguous triage state.

**SAMI latency:** If AI confidence score is unavailable at panel render time, display alert without recommendation chip — do not block panel load or display error state for individual missing scores.

**SAMI API failure:** If SAMI service is fully unavailable, panel must degrade gracefully — show alerts with manual triage options only; do not surface an error that implies alerts are inaccessible.

**Cross-tenant scope:** Alert aggregation must enforce MSP tenant access permissions at the API level, not only in the UI — never surface alerts outside the user's authorized tenant scope.

**Malformed SAMI response:** Panel must not break if SAMI returns null, unexpected enum, or out-of-range confidence score — handle gracefully with fallback rendering.

---

### Testable Checkboxes

**Dashboard Rendering**
- [ ] SAMI triage panel renders on UM Dashboard for MSP role when feature flag is enabled
- [ ] Panel does not render when feature flag is disabled — no broken or empty container visible
- [ ] Untriaged alert count badge displays correct real-time count
- [ ] Alerts render sorted by SAMI confidence score descending
- [ ] Empty state renders correctly when untriaged count = 0

**AI Recommendations**
- [ ] SAMI recommendation chip displays for alerts at or above confidence threshold
- [ ] Alerts below threshold render without chip — no broken or placeholder state
- [ ] Recommendation chip label accurately reflects SAMI output (Acknowledge / Escalate / Dismiss)

**Triage Actions**
- [ ] All triage actions (Acknowledge / Escalate / Dismiss) are available per alert
- [ ] Completed triage removes alert from untriaged queue immediately
- [ ] Untriaged badge count decrements correctly after each triage action
- [ ] Triage event is logged with correct: actor, timestamp, action, tenant ID
- [ ] SAMI acceptance flag is set correctly when user action matches recommendation
- [ ] Escalate action triggers the defined escalation workflow

**Bulk Triage (MSP)**
- [ ] Bulk triage action available for MSP role only
- [ ] Partial bulk triage failure does not leave the queue in an inconsistent state
- [ ] Untriaged count updates correctly after bulk action completes

**Suppression**
- [ ] Already-triaged alerts do not reappear in the untriaged queue
- [ ] Alerts from deactivated tenants are suppressed from the panel
- [ ] Alerts below SAMI confidence threshold remain in queue — suppression applies to chip only

**SAMI Degraded States**
- [ ] Panel loads and displays alerts when SAMI confidence score is unavailable — no chip shown, no error
- [ ] Panel degrades to manual-triage-only mode when SAMI service is unavailable — no error blocking alert access

**Scope & Permissions**
- [ ] MSP users see only alerts within their authorized tenant scope
- [ ] Cross-tenant alert query is enforced at the API level — not filterable via UI manipulation
- [ ] Enterprise IT Admin does not see cross-tenant aggregation or bulk triage controls

---

## ⚠ Edge Cases to Verify Before Handoff

- **Concurrent triage conflict:** No conflict resolution strategy defined yet — must be decided before engineering picks this up.
- **Escalation target undefined:** Post-action escalation workflow destination (system/team) is TBD — Epic cannot be marked done without this defined.
- **Baseline metrics missing:** Success metrics targets are all TBD — baseline alert volume and triage time data required before launch criteria can be set.
- **SAMI confidence threshold:** Chip display threshold not yet defined — PM and data science alignment required.
- **Bulk triage failure handling:** Behavior on partial failure during bulk action not fully specified — define before QA.

---

*Does this format work, or adjust?*
- **Switch format** — General / Conditional Logic / Sequential Flows / Performance & Reliability / Integration & API Contract
- **Customise** — describe your intent
- **Good to go**
