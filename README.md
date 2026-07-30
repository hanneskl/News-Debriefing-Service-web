# News Debriefing Service — Web

Public web front for the [News Debriefing Service](https://github.com/hanneskl/News-Debriefing-Service)
(the pipeline + MCP server live in that private repo). Sister of
`podcast-debriefing-service-web`.

Served via **GitHub Pages** at `https://hanneskl.github.io/News-Debriefing-Service-web/`.

## Live now

- **`oauth/consent.html`** — the OAuth 2.1 login + consent page for the remote
  MCP server. Supabase's OAuth server redirects here (`authorization_path`); the
  user signs in (email OTP) and approves, then is redirected back to the MCP
  client with an authorization code. Static, no secrets (only the public anon
  key + project URL).

  It lives here on GitHub Pages rather than in a Supabase Edge Function because
  Supabase forces `text/plain` + a script-blocking CSP on HTML served from its
  own domains, so the page's JavaScript would never run.

## Notes

- Static site, no build step. The consent page is plain HTML +
  `@supabase/supabase-js` from a CDN.
