# OWASP Top 10 Verification Checklist

## A01: Broken Access Control
- [ ] Verify principle of least privilege
- [ ] Check that users cannot act outside their intended permissions
- [ ] Verify CORS configuration is restrictive
- [ ] Test for IDOR (Insecure Direct Object References)

## A02: Cryptographic Failures
- [ ] Verify sensitive data is encrypted at rest
- [ ] Verify TLS for all data in transit
- [ ] Check for hardcoded secrets or API keys
- [ ] Verify password hashing uses bcrypt/scrypt/argon2

## A03: Injection
- [ ] Test for SQL injection on all database queries
- [ ] Test for NoSQL injection
- [ ] Test for command injection
- [ ] Verify parameterized queries are used everywhere

## A04: Insecure Design
- [ ] Verify threat modeling was performed
- [ ] Check for business logic flaws
- [ ] Verify rate limiting on sensitive endpoints

## A05: Security Misconfiguration
- [ ] Check for default credentials
- [ ] Verify error messages don't leak stack traces
- [ ] Check HTTP security headers
- [ ] Verify unnecessary features are disabled

## A06: Vulnerable and Outdated Components
- [ ] Run dependency audit (npm audit, pip audit, etc.)
- [ ] Check for known CVEs in dependencies
- [ ] Verify all dependencies are actively maintained

## A07: Identification and Authentication Failures
- [ ] Verify session management
- [ ] Check for brute force protection
- [ ] Verify MFA where required

## A08: Software and Data Integrity Failures
- [ ] Verify CI/CD pipeline integrity
- [ ] Check for unsigned/unverified updates
- [ ] Verify deserialization safety

## A09: Security Logging and Monitoring Failures
- [ ] Verify authentication events are logged
- [ ] Verify failed access attempts are logged
- [ ] Check that logs don't contain sensitive data

## A10: Server-Side Request Forgery (SSRF)
- [ ] Verify URL validation on all user-supplied URLs
- [ ] Check for internal network access from user input
