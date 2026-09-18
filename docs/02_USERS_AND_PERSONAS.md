# CanadaCare — Users and Personas

**Status:** Draft hypotheses for discovery  
**Version:** 0.1  
**Last updated:** 2026-09-17

> These are provisional workflow personas, not research findings or claims about every patient or provider. Validate them through interviews and usability testing.

## 1. Primary user groups

### Persona A — Patient managing a referral

**Situation:** Has been referred for a service and wants to understand what happens next.

**Goals**
- Confirm that the referral was received.
- Understand the current status and next step.
- Know whether they need to provide information or take action.
- Manage appointment details and receive clear notifications.
- Access information in an understandable and accessible format.

**Possible pain points to validate**
- Uncertainty about which organization currently has the referral.
- Having to contact multiple offices for updates.
- Separate portals or communication channels.
- Difficulty understanding what “pending,” “triaged,” or “scheduled” means.

**Design considerations**
- Plain-language status labels and timestamps.
- Accessible, mobile-friendly interface.
- Clear contact route and non-digital alternative.
- Avoid displaying another patient’s information on shared devices.
- Do not imply clinical urgency or provide triage advice.

### Persona B — Referring clinician or clinic staff

**Situation:** Submits a referral and may need to confirm receipt, provide missing information, or respond to follow-up.

**Goals**
- Submit complete referrals through approved workflows.
- See whether the referral was received and whether more information is required.
- Avoid duplicate submissions and unnecessary calls.
- Maintain a clear record of actions.

**Possible pain points to validate**
- Different referral requirements or systems.
- Unclear receipt or status feedback.
- Re-entering information across systems.
- Manual follow-up to resolve incomplete submissions.

**Design considerations**
- Role-based access and minimum necessary information.
- Clear validation and error messages.
- Traceable submission and status history.
- No unsupported clinical decision-making.

### Persona C — Referral / appointment coordinator

**Situation:** Manages incoming referrals, queues, scheduling communications, or cancellation lists.

**Goals**
- Work from an accurate queue.
- Identify missing information and next actions.
- Apply organization-approved eligibility and prioritization rules.
- Communicate appointment offers and outcomes.
- Reduce avoidable duplicate work.

**Possible pain points to validate**
- Multiple work queues or manual spreadsheets.
- Repeated status inquiries.
- Difficulty coordinating cancellation offers.
- Unclear ownership at handoffs.

**Design considerations**
- Explicit queue ownership and status definitions.
- Human confirmation for consequential scheduling actions.
- Audit trail for changes and offers.
- Do not override clinical triage or organizational policy.

### Persona D — Healthcare IT / privacy / security stakeholder

**Situation:** Evaluates whether a new application can integrate safely with existing infrastructure and governance.

**Goals**
- Understand data flows, system boundaries, and responsibilities.
- Ensure identity, authorization, audit, retention, and incident processes are defined.
- Limit integration risk and vendor burden.
- Verify standards, contractual authority, and operational readiness.

**Possible concerns to validate**
- Unclear data stewardship or accountability.
- Integration and vendor constraints.
- Privacy impact and threat exposure.
- Support, monitoring, incident response, and lifecycle costs.

**Design considerations**
- Documented architecture and data inventory.
- Least privilege, auditable access, secure defaults.
- Tested integration contracts and failure handling.
- No production integration without formal approval.

## 2. Secondary stakeholders

- Accessibility advocates and patient advisory groups.
- Hospital/clinic operations leaders.
- Regional digital health and referral program teams.
- Information governance, legal, procurement, and clinical safety teams.
- Integration vendors and system administrators.

## 3. Interview plan

For each interview, record:
- Date and stakeholder role (avoid unnecessary personal details).
- Workflow and service line discussed.
- Current tools and handoffs.
- Most frequent exceptions and failure cases.
- Existing workarounds.
- Impact and frequency, where the participant can reasonably estimate.
- What is already working well.
- Evidence that could confirm or disprove each hypothesis.
- Permission and confidentiality conditions for notes.

## 4. Neutral interview questions

1. Could you walk me through the process from referral submission to appointment completion?
2. Which systems or communication channels are involved at each step?
3. Where do delays, uncertainty, repeated work, or errors occur, if anywhere?
4. How does a patient learn that a referral was received or needs more information?
5. How are cancellations and earlier appointment opportunities handled today?
6. Which existing portal or service already addresses parts of this process?
7. What must never be changed or automated?
8. What data would a coordination tool need, and who would authorize access?
9. How would you measure whether a change helped?
10. What would make a new tool unacceptable or duplicative?

## 5. Persona validation tracker

| Persona | Interviews planned | Evidence gathered | Key assumptions changed |
|---|---:|---|---|
| Patient | TBD | TBD | TBD |
| Referring provider/staff | TBD | TBD | TBD |
| Coordinator | TBD | TBD | TBD |
| IT/privacy/security | TBD | TBD | TBD |
