# Security Enforcement Policy

## Non-Negotiable Security Rules

All agents in the surepost system are bound by the following security rules.
The SECURITY_AGENT has veto power over any deployment that violates these rules.

---

## Rule 1: OAuth Token Encryption
- ALL social media OAuth tokens (access + refresh) must be encrypted with AES-256-GCM before storage
- Master key derived from environment variable using PBKDF2-SHA256 (100,000 iterations)
- Each token encrypted with unique random nonce
- Stored format: nonce (12 bytes) || ciphertext || auth_tag (16 bytes)
- VIOLATION: blocking deployment

## Rule 2: No Plaintext Secrets
- Zero secrets in codebase, config files, or git history
- All secrets from environment variables or HashiCorp Vault
- No hardcoded API keys, passwords, or connection strings
- VIOLATION: blocking deployment

## Rule 3: Parameterized Queries Only
- No string interpolation in SQL queries - ever
- Use pgx v5 parameter binding exclusively
- Code review must flag any string concatenation in database queries
- VIOLATION: blocking deployment

## Rule 4: Input Validation on All Endpoints
- All API inputs validated with go-playground/validator before processing
- Schema validation before any business logic executes
- Reject malformed input with 400 Bad Request
- VIOLATION: blocking deployment

## Rule 5: JWT Security
- Algorithm: RS256 (RSA 4096-bit keypair)
- Access token TTL: 15 minutes maximum
- Refresh token TTL: 7 days maximum
- Token ID (JTI) required for revocation
- Device fingerprint binding mandatory
- VIOLATION: immediate rollback

## Rule 6: Rate Limiting
- Global: 100 requests/minute per user
- Per-endpoint: 20 requests/minute per user
- Authentication endpoints: 10 attempts/15 minutes per IP
- Rate limit headers returned on every response
- VIOLATION: immediate rollback

## Rule 7: Security Headers
Required on every response:
- Content-Security-Policy
- Strict-Transport-Security (max-age=31536000; includeSubDomains)
- X-Frame-Options: DENY
- X-Content-Type-Options: nosniff
- Referrer-Policy: strict-origin-when-cross-origin
- VIOLATION: blocking deployment

## Rule 8: GDPR Compliance
- Cascade delete ALL user data on account deletion (including encrypted tokens)
- Data export endpoint must return all user data within 30 days
- No user data retained after deletion request
- Audit log of all data access
- VIOLATION: blocking deployment

## Rule 9: Password Security
- Algorithm: Argon2id
- Memory: 64MB
- Iterations: 3
- Parallelism: 2
- Never store plaintext passwords
- Never log passwords in any form
- VIOLATION: blocking deployment

## Rule 10: Audit Logging
- All authentication events logged (login, logout, failed attempts)
- All social token access logged (who accessed, when, what operation)
- All admin operations logged
- Audit logs append-only, never deletable
- VIOLATION: blocking deployment

---

## Security Agent Contact
Any security concern must be escalated to the SECURITY_AGENT immediately.
No deployment proceeds without security agent sign-off.
