# Evidence Status

## Confirmed in the working investigation

- Network configuration and VirtualBox host-only connectivity were verified.
- The Medusa backend was confirmed listening on TCP port 9000.
- Baseline `/search?q=test` returned `[]`.
- Crafted `/search` input returned a product record in the authorized local lab.
- Week 4 reconnaissance and OAuth artifacts are documented in the existing project record.

## Still required before final public submission

- Redacted dedicated SSO bypass screenshot/log, if available.
- Redacted dedicated Redis exposure screenshot/log, if available.
- Final public GitHub repository URL inserted into the report.
- Logged-out/incognito verification that the repository is public and opens correctly.

## Evidence rule

Do not create substitute evidence for a test that was not actually performed. If an artifact cannot be recovered, record the limitation in the report instead.
