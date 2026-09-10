# SSO Bypass Evidence

## Case
SSO Authorization Logic Flaw

## Source
Operation Secure Core — Week 4 Class 1 authorized laboratory material.

## Documented Test
The Week 4 lab instructed the tester to obtain a normal student authentication token and then submit that token to the /validate endpoint while supplying a different user_id.

Example test:

POST /validate
Authorization: Bearer STUDENT_TOKEN

{"user_id":2}

## Expected Vulnerable Result
The lab documents that the application could return:

{"valid":true,"identity":{"id":2,"role":"admin"}}

This demonstrates an authorization-logic flaw where the server trusts the client-supplied identity rather than the identity represented by the verified authentication token.

## Vulnerable Logic
const requestedId = req.body.user_id;

The Week 4 material identifies this as the vulnerable behavior.

## OWASP Mapping
Primary mapping: A01 — Broken Access Control.

The appropriate defensive control is to derive the authenticated identity from verified token claims and enforce authorization server-side. A client-supplied user_id must not override the authenticated identity.

## Evidence Limitation
This file records the documented Week 4 laboratory evidence and procedure. A dedicated SSO screenshot was not available in the final-project evidence folder, so no screenshot or live reproduction is claimed here.

## Security Note
No real credentials, access tokens, passwords, or private keys are included.
