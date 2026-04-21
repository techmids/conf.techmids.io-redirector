# conf.techmids.io-redirector

Redirects [conf.techmids.io](https://conf.techmids.io) → [conf.techmids.org](https://conf.techmids.org) via GitHub Pages, deployed automatically on push to `main`.

## Setup

1. **GitHub Pages** — go to *Settings → Pages* and set the source to **GitHub Actions**.
2. **DNS** — add a `CNAME` record pointing `conf.techmids.io` to `techmids.github.io`.
