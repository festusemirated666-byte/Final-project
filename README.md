# Mapping Authentication and Injection Attacks to OWASP Defensive Controls

Individual cybersecurity final project.

## Objective
Investigate four authorized laboratory attack cases and map each to the most directly applicable OWASP Top 10:2021 defensive category/control.

## Cases
1. OAuth authorization-code interception/replay
2. SSO authorization bypass
3. SQL injection
4. Redis security misconfiguration

## Primary mapping
| Case | OWASP | Primary control |
|---|---|---|
| OAuth replay | A07 | PKCE, binding, short lifetime, single-use, TLS |
| SSO bypass | A01 | Trusted token subject + server-side authorization |
| SQL injection | A03 | Parameterized queries / safe ORM APIs |
| Redis exposure | A05 | Authentication + network restriction + least privilege |

## Repository
- `report/final-report.pdf`
- `evidence/evidence-index.md`
- `evidence/test-matrix.md`
- `analysis/risk-register.md`
- `ai/AI_PROMPT_JOURNAL.md`
- `references/sources.md`
- `tests/`
- `src/`

## Important
The final report must contain the public GitHub repository link before LMS submission. Replace the placeholder learner/institution fields and add only redacted authorized evidence.

## Security
Never commit private keys, passwords, API keys, access tokens, seed phrases, `.env` files, production credentials, or unnecessary personal information.
