# CanadaCare — Gap Analysis and Product Hypothesis

**Status:** Hypothesis; not validated  
**Version:** 0.1  
**Last updated:** 2026-09-17

## 1. Working hypothesis

CanadaCare may be valuable as a **secure patient-visibility and coordination layer** for a specific referral pathway across participating organizations, provided discovery confirms a material workflow gap and the platform can integrate under appropriate governance.

This is not yet a finding. The gap must be demonstrated against existing portals, referral services, and actual operating procedures.

## 2. Candidate gaps to investigate

| Candidate gap | Evidence needed | Potential product response if validated |
|---|---|---|
| Patient cannot easily tell which organization owns the next step | Patient journey interviews; status and communication review | Plain-language referral timeline with accountable source and next action |
| Status information is split across participating systems | System mapping; stakeholder confirmation; authorized API review | Consolidated status view with timestamps and source attribution |
| Eligible appointment opportunities are hard to coordinate across participants | Current waitlist policy; slot and eligibility workflow; stakeholder approval | Rules-based offer workflow, with authorized staff oversight |
| Patients repeat information or follow up manually | Patient/staff interviews; task frequency baseline | Reduce duplicate status inquiries and clarify handoffs |
| Organizations lack a shared view of operational coordination | Coordinator workflow; governance and data availability review | Limited operational dashboard using minimum necessary data |

## 3. Non-gaps / existing capabilities to account for

CanadaCare must explicitly account for:
- Hospital portals that already support booking or appointment management for selected services.
- Existing referral and central intake initiatives.
- Organization-specific waitlists, scheduling tickets, and cancellation workflows.
- Clinical systems that remain the authoritative source for clinical and scheduling data.
- Telephone, in-person, and other non-digital routes that must remain available where required.

## 4. Differentiation tests

Before claiming differentiation, answer:
1. Which exact user and workflow are underserved?
2. Which existing service already addresses the need?
3. What is the measurable unmet need?
4. Why can’t the existing service or system vendor address it?
5. What integration, governance, and procurement conditions apply?
6. Who owns the source-of-truth data and the scheduling decision?
7. Would users adopt another portal, or is embedding into existing workflows necessary?
8. What benefit can be measured without claiming to reduce clinical wait times broadly?

## 5. Candidate value proposition (conditional)

> For patients and care teams in a defined participating referral pathway, CanadaCare aims to make referral progress and approved appointment coordination easier to understand by connecting selected workflow information from existing systems—without replacing clinical systems or making clinical prioritization decisions.

Use this only after validating the workflow, authority, data access, and user need.

## 6. Go / revise / stop criteria

**Proceed to a focused prototype if:**
- Multiple relevant stakeholders confirm the same specific problem.
- Existing tools do not already adequately address it for the selected pathway.
- A plausible, authorized source of required data exists.
- The workflow owner supports testing a complementary solution.
- A measurable baseline and safe synthetic-data prototype can be defined.

**Revise the hypothesis if:**
- The need exists but a different user, pathway, or integration point is more appropriate.
- Existing tools cover most of the workflow but leave a narrower usability or communication issue.

**Stop or pivot if:**
- The target workflow is already adequately served.
- Required data cannot be accessed lawfully or operationally.
- No organization owns or supports the proposed workflow.
- The concept requires unsafe automation or unsupported clinical decisions.
