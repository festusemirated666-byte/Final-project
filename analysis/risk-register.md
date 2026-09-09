# Risk Register

| ID | Finding | OWASP | Priority | Recommended control |
|---|---|---|---|---|
| R1 | OAuth authorization-code replay | A07 | High | PKCE, binding, short lifetime, single-use, TLS |
| R2 | SSO authorization bypass | A01 | High | Server-side authorization using verified token subject |
| R3 | SQL injection | A03 | High | Parameterized queries / safe ORM APIs |
| R4 | Redis exposure | A05 | High | Authentication, network restriction, least privilege |

Ratings are qualitative and limited to the authorized lab context.
