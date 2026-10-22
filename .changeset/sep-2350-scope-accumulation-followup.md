---
'@modelcontextprotocol/client': patch
---

Keep previously granted OAuth scopes when a `401` leads to a new authorization. Automatic `401` handling in Streamable HTTP and legacy SSE adds the token's granted scope and every scope the transport has challenged or requested to the scope it selects; `withOAuth` adds the token's granted scope. The refresh token is still tried first. A step-up scope the authorization server refuses is no longer remembered for later requests. `auth()` accepts a new `retainScope` option for this.
