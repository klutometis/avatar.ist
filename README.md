# avatar.ist (static)

The public face of avatar.ist since 2026-11-18: the character gallery plus
the 1:40 demo cut, served by GitHub Pages at <https://www.avatar.ist>.

The live app (Next.js web + LiveKit/LemonSlice agent) is in
`~/prg/avatar` (`klutometis/avatar`). It ran on Railway (projects `avatar`
and `avatar-spark`) until 2026-11-18, when it was stopped: it had no real
traffic in 30 days, and its secrets leaked in the 2026-10-21 Railway breach.
The Railway projects were stopped, not deleted.

- `demo.mp4`: `~/prg/avatar/demo/avatar-funboarding.mp4`, remuxed with
  `-movflags +faststart` so it streams. `poster.jpg` is its frame at 2 s.
- `hosts/*.jpg`: copied from `~/prg/avatar/app/public/hosts/`.

DNS is on Cloudflare (zone avatar.ist): `www` is a grey CNAME to
`klutometis.github.io`; a redirect rule sends the apex and every other
subdomain (the old per-character hosts) to `https://www.avatar.ist`.

To bring the live demo back: redeploy the Railway services, rotate their
secrets (LiveKit, LemonSlice, Google OAuth, AUTH_SECRET), and point `www`
and `*` back at Railway.
