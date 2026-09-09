# Test Matrix

| Test ID | Scenario | Expected Result | Observed Result | Interpretation |
|---|---|---|---|---|
| T01 | Normal `/search?q=test` | Normal application response | `[]` | Baseline behavior |
| T02 | Crafted `/search` input | Input treated as data; no query manipulation | Product record returned | Consistent with the documented SQL-injection lab case |
| T03 | OAuth authorization-code first redemption | Valid exchange only for intended flow | Token obtained in authorized lab | Replay risk demonstrated |
| T04 | OAuth authorization-code second redemption | Reuse rejected | Original lab record documented replay | Single-use enforcement is required |
| T05 | SSO identity mismatch | Authorization denied | Client-supplied identity influenced result in lab | Broken access control |
| T06 | Redis unauthorized access | Connection denied | Unauthenticated access documented in Week 4 | Security misconfiguration |

> T03–T06 should be backed by the original redacted screenshots/logs before final public submission.
