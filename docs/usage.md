# Usage

```go
package main

import (
	"context"
	"fmt"

	"github.com/go-birdsite/twitter"
)

func main() {
	c := twitter.New()

	tl, err := c.UserTweets(context.Background(), "jack")
	if err != nil {
		panic(err) // 403/429 here means Twitter/X is blocking the request.
	}
	for _, tw := range tl.Tweets {
		fmt.Printf("@%s: %s (%d likes)\n", tw.Author, tw.Text, tw.Likes)
	}
}
```

Many profiles or rate states require a valid auth token — supply one with `WithAuthToken`. Blocked requests surface as errors (`403`/`429`), which indicate fragility, not a bug in the code.

For the complete, always-current API — every type and field — see
[pkg.go.dev/github.com/go-birdsite/twitter](https://pkg.go.dev/github.com/go-birdsite/twitter).
