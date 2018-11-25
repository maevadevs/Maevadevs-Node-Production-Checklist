# Security Checklist

## Security HTTP Headers Config

These can be easliy done using the `Helmet` module

- `Strict-Transport-Security`: Enforce secure connections to the server (HTTP over SSL/TLS)
- `X-Frame-Options`: Provide clickjacking protection
- `X-XSS-Protection`: Enable browser XSS filtering
- `X-Content-Type-Options`: Prevent browsers from MIME-sniffing a response away from the declared content-type
- `Content-Security-Policy`: Prevent a wide range of attacks, XSS and other cross-site injections

## Client-Side Sensitive Data

Make sure you are not exposing secrets and keys on the client-side

## Brute-Force Protection

Protect the login endpoint using rate-limiting. This can be easily done using the `ratelimiter` module
