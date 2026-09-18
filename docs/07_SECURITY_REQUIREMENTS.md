# CanadaCare — Initial Security Requirements

**Status:** Prototype security baseline; requires professional review before production  
**Version:** 0.1  
**Last updated:** 2026-09-17

## 1. Purpose and limitation

This document defines a starting security baseline for a synthetic-data academic prototype. It is not a legal opinion, privacy impact assessment, threat assessment approval, certification, or declaration of PHIPA compliance. Production use involving personal health information requires formal privacy, legal, clinical, security, architecture, and operational review with the responsible organizations.

## 2. Security principles

- Privacy and security by design and default.
- Data minimization and purpose limitation.
- Least privilege and separation of duties.
- Explicit trust boundaries and authenticated service-to-service communication.
- Defense in depth.
- Secure, auditable handling of consequential actions.
- Fail safely when identity, authorization, or integration state is uncertain.
- Accessibility and non-digital alternatives are part of safe service design.

## 3. Data classification and prototype boundary

| Data class | Prototype treatment |
|---|---|
| Public project information | May be used in documentation. |
| Synthetic patient and referral data | Allowed only when clearly fictional and not derived from real people. |
| Credentials, tokens, secrets | Never commit to source control or expose in logs. |
| Real PHI / production identifiers | Out of scope; do not collect, import, or test with them. |

Use fabricated names, dates, identifiers, and clinical details. Avoid “de-identified” real records unless an approved process and authorization explicitly permit it; for this prototype, synthetic data is the default.

## 4. Identity and authentication

- Use a maintained identity provider (e.g., Keycloak with OIDC) rather than inventing password handling.
- Require authenticated access to patient- and staff-specific functions.
- Use MFA for privileged or staff access in any production-oriented design; evaluate patient MFA based on risk and approved usability requirements.
- Use secure session/token handling appropriate to the deployment.
- Protect account recovery and session termination.
- Do not place long-lived tokens or sensitive health data in browser local storage.
- Do not rely on hidden UI elements as access control.

## 5. Authorization

- Enforce authorization on the Spring Boot backend for every protected request.
- Apply role and resource-level checks (e.g., patient may access only their own records; coordinator may access only assigned organization/queue).
- Deny by default.
- Validate ownership and organization scope server-side; never trust patient or organization IDs supplied by the client without checking.
- Separate read, update, offer creation, and administrative privileges.
- Require explicit authorization for exceptional access and log it if such a capability is ever introduced.

## 6. Data protection

- Use TLS for network traffic in any deployed environment.
- Use appropriate encryption at rest for databases, backups, and stored files.
- Keep secrets in a secrets manager or protected environment configuration; rotate them when exposed.
- Minimize data returned by APIs.
- Avoid sensitive data in URLs, analytics, error messages, and logs.
- Define retention and deletion behavior before storing any non-synthetic data.
- Protect backups and test restoration procedures before production.

## 7. Application and API security

- Validate inputs server-side; use allowlists for state transitions and enumerated fields.
- Apply rate limits and abuse protections appropriate to exposed endpoints.
- Use safe error responses; do not return stack traces.
- Protect against injection, broken access control, insecure direct object references, CSRF where applicable, and unsafe CORS configuration.
- Restrict CORS to approved origins; do not use permissive wildcard settings with credentials.
- Keep dependencies and base images patched; scan for known vulnerabilities.
- Use parameterized database access and avoid unsafe dynamic SQL.
- Apply secure headers and appropriate content security policy at deployment.
- Validate integration payloads and handle malformed, duplicate, delayed, and out-of-order messages safely.

## 8. Audit and monitoring

For relevant sensitive or consequential actions, record:
- Event type and timestamp.
- Authenticated actor identifier (use synthetic identifiers in the prototype).
- Target record reference (synthetic).
- Outcome (success/failure) and reason category where appropriate.
- Relevant organization/role context.
- Correlation ID for troubleshooting.

Do not log passwords, access tokens, full clinical payloads, or unnecessary PHI. Protect audit logs against unauthorized modification and access. Define retention and review ownership before production.

## 9. Secure development lifecycle

- Use protected branches and code review.
- Enable secret scanning and dependency scanning.
- Keep development, test, and production configurations separate.
- Use synthetic fixtures in tests.
- Test negative authorization cases, not only successful flows.
- Document security decisions and known risks.
- Track vulnerabilities to remediation and verify fixes.
- Produce a software bill of materials (SBOM) for release candidates where practical.

## 10. Prototype security test checklist

- [ ] Patient A cannot read or alter Patient B's referral.
- [ ] A coordinator cannot access another organization's queue.
- [ ] Unauthenticated requests to protected endpoints are rejected.
- [ ] Unauthorized status transitions are rejected.
- [ ] Invalid and oversized input is handled safely.
- [ ] Errors do not disclose stack traces or secrets.
- [ ] CORS allows only intended development origins.
- [ ] Secrets are absent from Git history and client bundles.
- [ ] Audit events are generated for defined actions.
- [ ] Logs contain no credentials or unnecessary sensitive data.
- [ ] Dependencies and container images are scanned.
- [ ] Demo uses only synthetic data.

## 11. Production-readiness items not yet satisfied

- Privacy impact assessment and applicable legal review.
- Data stewardship, custodian/agent roles, and contractual agreements.
- Approved threat/risk assessment and security architecture review.
- Identity proofing and account lifecycle design.
- Production key management, monitoring, incident response, and business continuity.
- Accessibility and clinical safety review where applicable.
- Integration approval, conformance testing, and operational support.
- Retention, access, correction, and breach-response procedures.
