# Fragility & Terms of Service

!!! danger "Read this before depending on the library"
    This is inherently fragile. Twitter/X changes and locks these endpoints, and many profiles or rate states require a valid auth token.

This client reads the **public syndication timeline endpoint** that powers embedded timeline widgets — it is not a documented, supported API. Twitter/X changes and locks these endpoints, and the response shape can change at any time, which surfaces as decode errors.

## What this means in practice

- Many profiles or rate states require a valid auth token (`WithAuthToken`).
- Requests can start returning **403 / 429** at any time when Twitter/X decides to block you; the library surfaces those as clear errors.
- The Go API is kept small and stable so your code survives the churn underneath — but the transport may break regardless.

## Your responsibility

Automated access to Twitter/X may violate its Terms of Service and/or
applicable law. **You are responsible for how you use this library** — use it
only for content and in ways you are authorised to access, and respect rate
limits. The maintainers cannot promise the underlying transport keeps working.
