# AI Assistance Record

## Prompt used
What defensive controls would have prevented OAuth code replay and the SSO logic flaw in my application? Map each attack to one OWASP control.

## Use of AI
AI was used to generate an initial defensive mapping and organize the analysis.

## Independent verification
The mappings were checked against official OWASP documentation. The SSO case was refined to A01 Broken Access Control as the primary mapping because the demonstrated weakness involved client-controlled identity data affecting authorization. OAuth replay remains primarily A07 because OWASP A07 includes capture-replay.

## Limitation
AI output was treated as a hypothesis and not as proof of the technical finding.

## Refinement
The final analysis distinguishes authentication from authorization and maps each case according to the observed failure mechanism.
