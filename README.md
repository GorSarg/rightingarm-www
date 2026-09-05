# rightingarm.com

The holding page for [Righting Arm](https://rightingarm.com). One self-contained file:
the logo is inlined as a data URI and the Google Fonts stylesheet is the only outbound
request, so it will sit on any static host with no build step.

This repository is **public only so GitHub Pages can serve it**. Nothing about the product
lives here — the application is private.

## Deploy

Served by GitHub Pages from `main`, root folder.

1. **Settings → Pages** → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.
2. **Settings → Pages → Custom domain**: `rightingarm.com`. The `CNAME` file in this repo
   sets the same thing and is what Pages reads on each deploy.
3. **GoDaddy DNS** — delete the parked/forwarding records first or they will win:

   | Type  | Name | Value                |
   |-------|------|----------------------|
   | A     | @    | 185.199.108.153      |
   | A     | @    | 185.199.109.153      |
   | A     | @    | 185.199.110.153      |
   | A     | @    | 185.199.111.153      |
   | CNAME | www  | gorsarg.github.io    |

   Optional IPv6, alongside the A records rather than instead of them:
   `2606:50c0:8000::153`, `:8001::153`, `:8002::153`, `:8003::153` as AAAA on `@`.

4. **Enforce HTTPS** in Settings → Pages once the certificate is issued — minutes to an hour.

Re-check the addresses against GitHub's current documentation before entering them; they
have changed before.

## Editing

`index.html` is hand-written, no build. The design lives in the `:root` custom properties at
the top: `--paper`, `--ink`, `--navy` (sampled from the logo), `--brass`, `--hairline`.
