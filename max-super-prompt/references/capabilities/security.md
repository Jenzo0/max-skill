# 🔒 Security Capabilities

> Load trigger: Code/Architect/DevOps mode with security-related request.

## OWASP Top 10 (Quick Reference)

| # | Risk | Mitigation |
|---|---|---|
| 1 | Broken Access Control | RBAC/ABAC, deny-by-default, server-side enforcement |
| 2 | Cryptographic Failures | No custom crypto, use bcrypt/Argon2 for passwords, TLS 1.3 |
| 3 | Injection | Parameterized queries, input validation, allow-lists |
| 4 | Insecure Design | Threat modeling, security requirements in design phase |
| 5 | Security Misconfiguration | Hardened defaults, disable debug in prod, automation |
| 6 | Vulnerable Components | SBOM, dependency scanning (Dependabot, Snyk, Trivy) |
| 7 | Auth Failures | MFA, rate limiting on login, account lockout, session rotation |
| 8 | Data Integrity Failures | Digital signatures, signed JWTs, integrity checks |
| 9 | Logging Failures | Structured logging, audit trails, log monitoring |
| 10 | SSRF | URL allow-lists, internal network isolation, disable redirects |

## Web Application Security

| Area | Practice |
|---|---|
| Headers | `Content-Security-Policy`, `Strict-Transport-Security`, `X-Content-Type-Options`, `X-Frame-Options` |
| CORS | Specific origin allow-list, not `*` for credentials |
| CSRF | SameSite cookies (Strict/Lax), CSRF tokens for state-changing requests |
| Rate Limiting | Token bucket (Redis), sliding window per user/IP/endpoint |
| Input Validation | Allow-lists over denylists, Pydantic/Zod schemas, length limits |

## API Security

- JWT: short expiry (15min access, 7d refresh), rotation, blacklist on logout
- API keys: hashed storage (`bcrypt`), per-key rate limits, rotation policy
- OAuth 2.0: PKCE for mobile/SPA, validate `aud` and `iss` claims
- GraphQL: query depth limiting, amount limiting, complexity scoring, persisted operations

## Infrastructure Security

| Layer | Practice |
|---|---|
| Network | VPC isolation, security groups, WAF, DDoS protection |
| Compute | Immutable infrastructure, minimal base images, regular patches |
| Secrets | Vault (HashiCorp), AWS Secrets Manager, GCP Secret Manager, env vars at runtime |
| Data at Rest | Encryption (AES-256), key rotation, HSM for master keys |
| Data in Transit | TLS 1.3, mTLS for service-to-service |

## Supply Chain Security

- SBOM generation (CycloneDX, SPDX)
- Dependency scanning (Dependabot, Renovate, Trivy, Grype)
- Image scanning (Trivy, Clair, Docker Scout)
- Sigstore / Cosign for container image signing
- SLSA framework for build integrity levels

## Authentication Protocols

| Protocol | Use Case | Implementation |
|---|---|---|
| OAuth 2.0 + OIDC | Third-party login, SSO | Authorization Code + PKCE, `openid` scope |
| SAML 2.0 | Enterprise SSO | XML assertions, IdP-initiated SSO, metadata exchange |
| WebAuthn / FIDO2 | Passwordless | Passkeys, hardware security keys (YubiKey), biometric |
| LDAP / Active Directory | Enterprise identity | LDAPS, Kerberos, group-based authorization |
