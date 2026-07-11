# go-birdsite

Pure-Go best-effort read client for public Twitter/X timelines.

!!! warning "Best-effort — read [Fragility & ToS](fragility.md) first"
    This is inherently fragile. Twitter/X changes and locks these endpoints, and many profiles or rate states require a valid auth token.

A pure-Go (**CGO=0**), dependency-free, **best-effort** read client for public Twitter/X profile timelines. It reads the public syndication timeline endpoint that powers embedded timeline widgets and extracts tweets from the `__NEXT_DATA__` JSON blob.

## Install

```sh
go get github.com/go-birdsite/twitter
```

## At a glance

- **CGO-free** (`CGO_ENABLED=0`), Go 1.26+ — builds for every 64-bit target.
- **Zero third-party dependencies** — standard library only.
- **Read-only** — this is a read client; it does not post or mutate.
- BSD-3-Clause.

See [Usage](usage.md) for a runnable example and [API reference](api.md) for the
full surface. The canonical, always-current reference is
[pkg.go.dev](https://pkg.go.dev/github.com/go-birdsite/twitter).
