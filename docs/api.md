# API reference

Source-verified against [`go-birdsite/twitter`](https://github.com/go-birdsite/twitter). The
authoritative, versioned reference is
[pkg.go.dev/github.com/go-birdsite/twitter](https://pkg.go.dev/github.com/go-birdsite/twitter).

## Constructor & methods

| Symbol | Purpose |
|---|---|
| `New(...Option) *Client` | Construct a client. |
| `(*Client).UserTweets(ctx, screenName) (*Timeline, error)` | Read a public profile's syndication timeline. |

## Options

Functional options passed to `New`:

| Option | Purpose |
|---|---|
| `WithAuthToken(token)` | Send an auth token — often required for a given profile / rate state. |
| `WithBaseURL(url)` | Override the request origin (useful for network-free tests). |
| `WithHTTPClient(*http.Client)` | Supply a custom HTTP client (timeouts, proxy, transport). |
| `WithUserAgent(ua)` | Set the `User-Agent` header. |

## Result types

| Type | Purpose |
|---|---|
| `Tweet` | A single tweet (`Author`, `Text`, `Likes`, `Media`, …). |
| `Media` | A media attachment on a tweet. |
| `Timeline` | The extracted list of `Tweets`. |

!!! note
    This table is a map, not the contract. Field-level details live in the
    [package reference](https://pkg.go.dev/github.com/go-birdsite/twitter) and the
    repository's `README`.
