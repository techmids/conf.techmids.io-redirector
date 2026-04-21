# conf.techmids.io-redirector

A simple redirect service that forwards all traffic from [conf.techmids.io](https://conf.techmids.io) to [conf.techmids.org](https://conf.techmids.org). It is hosted on GitHub Pages and deployed automatically via GitHub Actions.

## How it works

The site consists of a single `index.html` page that uses:

- **HTTP `meta refresh`** — instructs browsers to follow the redirect immediately.
- **JavaScript `window.location.replace`** — provides a faster client-side redirect for browsers with JavaScript enabled.
- **`<link rel="canonical">`** — signals to search engines that `conf.techmids.org` is the authoritative URL.

The `CNAME` file tells GitHub Pages to serve the site on the custom domain `conf.techmids.io`.

## CI/CD pipeline

The workflow is defined in [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml).

| Trigger | Behaviour |
|---------|-----------|
| Push to `main` | Automatically deploys to GitHub Pages |
| Manual (`workflow_dispatch`) | Allows one-off deploys from the Actions tab |

### Required GitHub repository settings

1. Go to **Settings → Pages**.
2. Under *Build and deployment*, set the source to **GitHub Actions**.
3. Ensure the `github-pages` environment exists (GitHub creates it automatically on the first successful deploy).

### DNS configuration

Add a `CNAME` record in your DNS provider pointing `conf.techmids.io` to `<org>.github.io` (replace `<org>` with the GitHub organisation name).

## Local preview

Open `index.html` directly in a browser. You will be redirected to `conf.techmids.org` immediately.
