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

This can be easily done using the `ratelimiter` module or using a simple middleware

Protect the login endpoint using rate-limiting. 

## Cookie Flags

These can be easily done using the `cookie` or `cookie-session` modules

- `secure`: This attribute tells the browser to only send the cookie if the request is being sent over HTTPS
- `HttpOnly`: This attribute is used to help prevent attacks such as XSS: It does not allow the cookie to be accessed via JavaScript

## Cookie Scope

These can be easily done using the `cookie` or `cookie-session` modules

- `domain`: This attribute is used to compare against the domain of the server in which the URL is being requested. If the domain matches or if it is a sub-domain, then the path attribute will be checked next.
- `path`:  In addition to the domain, the URL path that the cookie is valid for can be specified. If the domain and path match, then the cookie will be sent in the request.
- `expires`: This attribute is used to set persistent cookies, since the cookie does not expire until the set date is exceeded.

## CSRF Protection

These can be easily done using the `csrf` or the `csurf` modules

## XSS Protection

Filter and sanitize all user inputs, both at the client-side (at submission) and server-side (before usage)

## SQL Injection Protection

- Use parameterized queries or prepared statements: Don't inject user inputs into the sql query
- `sqlmap` service can be used to test for SQL Injections


