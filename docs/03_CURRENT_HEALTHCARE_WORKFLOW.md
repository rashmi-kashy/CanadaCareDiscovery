# CanadaCare — Current Healthcare Workflow

**Status:** Initial generic workflow; validate locally  
**Version:** 0.1  
**Last updated:** 2026-09-17

## 1. Purpose

This document provides a **working map** of a referral-to-appointment journey. It is not a definitive description of every Ontario pathway. The exact steps, terminology, systems, urgency rules, and responsibilities vary by service, organization, and region.

## 2. Generic journey to validate

1. **Clinical consultation:** A patient discusses a concern with an authorized healthcare provider.
2. **Referral decision:** The provider determines whether a referral or diagnostic request is appropriate under the applicable clinical workflow.
3. **Referral creation:** The provider or authorized staff completes the required referral information and supporting documentation.
4. **Submission:** The referral is sent through the applicable channel or system.
5. **Receipt and validation:** The receiving organization checks receipt and whether required information is present.
6. **Clinical review / triage:** Where applicable, authorized clinical personnel review and prioritize according to the pathway’s rules.
7. **Queue or destination management:** The referral is assigned, routed, or placed into an appropriate queue.
8. **Appointment scheduling:** The organization schedules the appointment or provides an approved self-booking or appointment-selection process, where available.
9. **Patient communication:** The patient receives relevant appointment details, instructions, and any required preparation information.
10. **Changes / cancellation:** The patient or organization may reschedule, cancel, or manage an eligible waitlist/cancellation process.
11. **Care and follow-up:** The appointment occurs; subsequent results, follow-up, or referrals follow the relevant clinical workflow.

## 3. Exceptions and branches

The workflow may branch when:
- The referral is incomplete or requires clarification.
- The referral is redirected or declined under applicable rules.
- The patient cannot be reached.
- The patient requests a different location or time.
- The patient is eligible for self-booking, a scheduling ticket, or a waitlist offer.
- The appointment is canceled or the service has no available slots.
- The case is urgent and follows a distinct process.
- A patient requires accessibility, language, or non-digital support.

Do not encode clinical priority or eligibility rules from assumptions. Obtain approved rules from the relevant organization.

## 4. Current-state mapping worksheet

Complete one worksheet for each specific pathway and participating organization.

| Step | Patient action / experience | Staff action | System / channel | Data exchanged | Handoff / owner | Pain point evidence |
|---|---|---|---|---|---|---|
| Referral created | TBD | TBD | TBD | TBD | TBD | TBD |
| Referral submitted | TBD | TBD | TBD | TBD | TBD | TBD |
| Receipt / validation | TBD | TBD | TBD | TBD | TBD | TBD |
| Review / triage | TBD | TBD | TBD | TBD | TBD | TBD |
| Scheduling | TBD | TBD | TBD | TBD | TBD | TBD |
| Appointment changes | TBD | TBD | TBD | TBD | TBD | TBD |
| Appointment completed | TBD | TBD | TBD | TBD | TBD | TBD |

## 5. Questions for workflow discovery

- Which service line and geography are in scope?
- Is the referral sent to one organization, a central intake, or multiple destinations?
- What confirms receipt to the referring provider and patient?
- Which status values are actually used, and who owns each status?
- Who may change a destination, priority, appointment, or waitlist position?
- Are self-booking links or scheduling tickets offered? Under what eligibility rules?
- How are patient preferences, accessibility needs, and consent handled?
- Which parts are electronic, manual, phone-based, or paper-based?
- What are the operational and clinical consequences of a missed message or stale status?
- What is the approved source of truth for each data element?

## 6. Output required before MVP design

For the chosen pathway, produce:
- A validated current-state swimlane diagram.
- A system/context diagram.
- A data-flow and responsibility map.
- A list of exceptions and business rules.
- A baseline of relevant workflow measures.
- Stakeholder approval of the documented workflow.
