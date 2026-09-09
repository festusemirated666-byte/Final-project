# OWASP Mapping Verification

- Token hijacking/replay -> A07 Identification and Authentication Failures.
  Rationale: OWASP A07 includes capture-replay (CWE-294); the lab demonstrated authorization-code interception and replay.
- SSO bypass -> A01 Broken Access Control (primary).
  Rationale: the lab flaw trusted `req.body.user_id`; OWASP A01 explicitly covers parameter tampering and elevation of privilege. A07 remains contextually relevant.
- SQL injection -> A03 Injection.
  Rationale: OWASP A03 explicitly includes SQL injection and recommends parameterized/safe APIs.
- Redis exploitation -> A05 Security Misconfiguration (primary).
  Rationale: the enabling condition documented in the lab is unauthenticated Redis exposure; A05 addresses insecure hardening/configuration and unnecessary exposed services.
