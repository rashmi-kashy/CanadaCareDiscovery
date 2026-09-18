# CanadaCare — Problem Statement

**Status:** Discovery draft  
**Version:** 0.1  
**Last updated:** 2026-09-17

## 1. Working problem statement

Patients may experience a fragmented journey when they need a referral and appointment involving multiple healthcare organizations. They may need to contact different offices, use separate patient portals, wait for an organization to contact them, or seek clarification about referral status and next steps.

Individual hospitals and clinics may already provide online booking, appointment management, referral systems, and waitlists. CanadaCare must therefore not assume that these capabilities are universally absent. The problem to investigate is whether gaps remain **between participating organizations and systems**, and whether patients and staff experience avoidable uncertainty or manual coordination as a result.

## 2. Who experiences the problem?

Potentially affected groups include:
- Patients navigating referrals, appointment scheduling, rescheduling, or cancellations.
- Family physicians and other referring providers managing referral submissions and follow-up.
- Hospital and clinic referral coordinators managing queues, triage, appointment capacity, and communication.
- Healthcare IT, privacy, security, and operations teams responsible for safe integration and reliable workflows.

These are discovery hypotheses, not validated findings.

## 3. Problem dimensions to investigate

1. **Visibility:** Can patients understand whether a referral was received, is being reviewed, or requires action?
2. **Coordination:** Where do handoffs between organizations rely on manual follow-up?
3. **Appointment options:** Can patients see and act on eligible appointment options when more than one organization participates?
4. **Cancellation use:** How are newly available appointment slots offered to eligible patients?
5. **Staff workload:** Which administrative tasks are duplicated or require repeated status checks?
6. **Interoperability:** What data can be exchanged, under what standards, permissions, and operational agreements?
7. **Trust and accessibility:** Can the experience be used safely and accessibly by patients with different needs?

## 4. Why existing solutions do not automatically settle the question

Online booking and referral tools exist, including organization-specific portals and regional initiatives. Their existence does not establish that every patient journey is connected end-to-end. Conversely, a fragmented experience in one setting does not prove a province-wide or national gap.

CanadaCare should map existing services and validate the exact workflow, geography, service line, and user group before selecting an MVP.

## 5. Proposed discovery question

> For a clearly defined referral pathway in a specific Ontario region, where do patients and care teams encounter avoidable uncertainty or manual coordination between referral submission and appointment completion, and could a secure coordination layer improve that experience while working with existing systems?

## 6. Initial assumptions to validate

| ID | Hypothesis | How to validate |
|---|---|---|
| H1 | Patients lack clear, timely visibility into some referral steps. | Patient interviews; portal walkthroughs; workflow mapping. |
| H2 | Staff perform repeated manual status checks or coordination. | Coordinator interviews; task observation; process logs where authorized. |
| H3 | Eligible cancellation slots are not consistently matched to suitable patients. | Review current waitlist procedures and eligibility rules. |
| H4 | Participating organizations have data and integration constraints that affect coordination. | IT/vendor interviews; interface and governance review. |
| H5 | A new layer could complement, rather than duplicate, current provincial or local services. | Competitive scan; stakeholder review; technical discovery. |

## 7. Scope boundaries

CanadaCare is initially a **workflow coordination and patient-visibility concept**, not:
- A replacement for provincial health systems, hospital information systems, EMRs, or existing referral platforms.
- A diagnostic or treatment recommendation system.
- A guarantee of earlier appointments or reduced clinical wait times.
- A source of clinical triage decisions unless a future, appropriately governed and validated scope explicitly supports that function.
- A system for production personal health information during the academic prototype.

## 8. Desired outcomes to measure in a future pilot

Potential measures, to be selected with participating stakeholders:
- Time required for a patient or staff member to determine referral status.
- Number of manual follow-up contacts per referral.
- Time from referral receipt to first patient-facing status update.
- Percentage of eligible cancellation slots successfully offered and filled.
- Patient comprehension of status and next steps.
- Staff usability and workload.
- Integration reliability, access-control correctness, and security findings.

Do not claim improvement until measured against a defined baseline.

## 9. Evidence and source log

Add verified sources, interview dates, stakeholder roles (without unnecessary personal identifiers), and notes here. Distinguish published evidence from interview observations and team assumptions.

| Source / date | Evidence or observation | Limitation |
|---|---|---|
| To be completed | To be completed | To be completed |
