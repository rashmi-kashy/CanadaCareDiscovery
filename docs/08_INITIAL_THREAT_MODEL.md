# CanadaCare — Initial Threat Model

**Status:** First-pass STRIDE-style model for synthetic prototype  
**Version:** 0.1  
**Last updated:** 2026-09-17

## 1. Purpose and assumptions

This is an initial threat-model worksheet, not a completed security assessment. It describes a proposed React + Vite frontend, Spring Boot API, PostgreSQL database, and development identity provider. The prototype uses synthetic data only and has no production healthcare integrations.

Revisit this model whenever the architecture, data, integrations, roles, or deployment changes.

## 2. System overview

**Components**
- Patient / coordinator browser UI (React + Vite).
- Spring Boot REST API.
- Identity provider (e.g., Keycloak / OIDC).
- PostgreSQL database.
- Audit/event storage.
- Optional simulated FHIR/HL7 adapter.
- Developer workstation and CI pipeline.
- Deployment/reverse proxy and container environment.

**Trust boundaries**
1. Browser to API.
2. API to identity provider.
3. API to database.
4. API to integration adapter or external system.
5. Developer/CI environment to deployable artifact.
6. Staff role boundary between organizations and queues.

## 3. Data-flow summary

1. User authenticates through the identity provider.
2. Browser obtains/uses the configured session or token.
3. Browser sends API request over HTTPS in deployed environments.
4. API validates authentication and authorization.
5. API reads or updates permitted records in PostgreSQL.
6. API records relevant audit events.
7. API returns minimum necessary data to the browser.
8. If enabled, an adapter exchanges validated synthetic messages with a simulator.

## 4. STRIDE threat register

| ID | STRIDE | Threat scenario | Potential impact | Initial mitigation | Validation / test |
|---|---|---|---|---|---|
| T1 | Spoofing | Attacker uses a stolen or guessed account/session. | Unauthorized access to records or actions. | OIDC; secure session handling; MFA for privileged users; account protections. | Test expired/revoked sessions and account lifecycle. |
| T2 | Tampering | User alters a referral ID, status, or organization ID in an API request. | Cross-patient access or unauthorized workflow change. | Server-side ownership checks; allowlisted transitions; input validation. | IDOR and negative authorization tests. |
| T3 | Repudiation | User denies changing a referral or issuing an offer. | Weak accountability and difficult investigation. | Protected audit events with actor, timestamp, target, outcome. | Verify event creation and access restrictions. |
| T4 | Information disclosure | API returns another patient's data or logs sensitive payloads. | Privacy breach and loss of trust. | Resource-level authorization; data minimization; safe logging. | Cross-account tests; log review. |
| T5 | Denial of service | Repeated requests or oversized inputs exhaust API/database resources. | Service interruption. | Rate limits, request limits, timeouts, resource limits, monitoring. | Load and abuse tests appropriate to prototype. |
| T6 | Elevation of privilege | Patient manipulates client-side role or accesses staff endpoint. | Unauthorized administrative actions. | Backend authorization; roles/claims validated server-side; deny by default. | Attempt staff API access with patient account. |
| T7 | Integration spoofing | Simulated or future external sender submits forged or replayed messages. | Incorrect status or appointment data. | Authenticated integration, message validation, replay/idempotency controls. | Invalid signature/auth and duplicate-message tests. |
| T8 | Supply-chain compromise | Vulnerable or malicious dependency/container enters build. | Code execution, data exposure, service compromise. | Dependency pinning/updates, scanning, review, SBOM, trusted build process. | CI scans and dependency review. |
| T9 | Secret exposure | API key, DB password, or signing secret is committed or bundled into frontend. | Account or system compromise. | Secret manager/environment injection; scanning; rotation. | Scan repository and built frontend. |
| T10 | Misconfiguration | Permissive CORS, debug endpoints, or default credentials remain enabled. | Unauthorized access or information disclosure. | Secure configuration profiles; production-like review; no defaults. | Configuration checklist and deployment scan. |
| T11 | Audit compromise | Attacker alters or deletes audit events. | Reduced ability to investigate. | Restrict write/read permissions; append-oriented storage; monitoring. | Verify application roles cannot modify prior events. |
| T12 | Unsafe workflow automation | Incorrect eligibility/status rule offers an appointment to an inappropriate patient. | Confusion, unfair access, operational or clinical harm. | Use approved rules; staff oversight; no clinical triage automation; clear offer semantics. | Stakeholder review and scenario-based tests. |

## 5. Assets and security objectives

| Asset | Security objective |
|---|---|
| Synthetic referral records | Correct access boundaries and integrity. |
| User accounts / sessions | Prevent impersonation and privilege abuse. |
| Workflow state | Only authorized, valid transitions. |
| Audit events | Accountability and tamper resistance. |
| Secrets / signing keys | Confidentiality and controlled use. |
| Integration messages | Authenticity, integrity, validation, and replay handling. |
| Build artifacts | Integrity and traceable provenance. |

## 6. Abuse cases to test

- Patient changes a record identifier to access another patient's referral.
- Patient calls a coordinator-only endpoint directly.
- Coordinator changes a record belonging to another organization.
- Unauthenticated user calls a protected endpoint.
- User submits an invalid or repeated state transition.
- Malformed integration payload changes workflow state.
- Duplicate message creates duplicate appointment offers.
- Sensitive data appears in URL, browser storage, console, or logs.
- A dependency or secret scan identifies a release blocker.

## 7. Risk-rating worksheet

Use the team's agreed likelihood/impact scale; do not assign numeric ratings until the team defines it.

| Threat ID | Likelihood rationale | Impact rationale | Current controls | Residual risk | Owner | Due date |
|---|---|---|---|---|---|---|
| T1–T12 | TBD | TBD | TBD | TBD | TBD | TBD |

## 8. Review checklist

- [ ] Confirm system diagram and all data flows.
- [ ] Identify data classification and legal/organizational responsibilities.
- [ ] Confirm all user roles and resource ownership rules.
- [ ] Review authentication, session, and account recovery design.
- [ ] Review integration trust and message validation.
- [ ] Review logging, monitoring, and incident response.
- [ ] Run abuse-case tests and record evidence.
- [ ] Assign owners and dates to mitigations.
- [ ] Revisit after any significant architecture or scope change.
