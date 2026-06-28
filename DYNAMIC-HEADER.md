# Time-of-day header — setup

Four sky variants + a Vercel function that serves the right one based on the
current hour, so your profile header changes through the day.

```
dawn   05:00–08:00   cool blue → soft peach
day    08:00–17:00   bright blue, sun, white name
dusk   17:00–20:00   indigo → magenta → gold   (your default)
night  20:00–05:00   deep navy, moon, lit windows
```

## Option A — dynamic (recommended)

1. Drop `api/header.js` into any Vercel project (your portfolio works great).
   No dependencies, no package.json needed — Vercel auto-detects `/api`.
2. Open `api/header.js` and set `TZ` to your timezone (default `America/New_York`).
3. Deploy. Your endpoint is `https://YOUR-PROJECT.vercel.app/api/header`.
4. In your profile README, point the header image at the endpoint:

   ```md
   ![Rohith M](https://YOUR-PROJECT.vercel.app/api/header)
   ```

> Note: GitHub proxies/caches images, so the sky won't flip the *instant* the
> hour changes — it rolls over within a few minutes of each phase. That's normal.

## Option B — static

Don't want to deploy anything? Just pick one `header-*.svg`, rename it to
`header.svg`, and use it like the original. (Your README currently points at
`./header.svg`.)
