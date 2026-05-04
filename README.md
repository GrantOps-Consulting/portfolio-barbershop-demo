# portfolio-barbershop-demo

Single-file static portfolio demo for GrantOps Consulting's homepage `ProjectsGrid`. Brand: **Trongate Barber Co.** — fictional modern Glasgow barbershop. Showcases a Nearcut booking integration (link-out pattern, no embedded iframe).

Deployed to `barbershop-demo.grantopsconsulting.com` via GitHub Actions OIDC on push to `main`. Infrastructure (S3 + Cloudflare DNS) lives in `GrantOps-Consulting/grantops-web-infra` under client slug `portfolio-barbershop-demo`.

## Notes

- `<meta name="robots" content="noindex, nofollow">` — only intended path is the curated link from grantopsconsulting.com.
- Footer carries: *Portfolio demo by GrantOps Consulting — no real business sits at this address. View our work at [grantopsconsulting.com](https://grantopsconsulting.com/).*
- "Book online" CTA points at https://nearcut.com/en-GB/ — no live tenant configured. To upgrade to an embedded iframe, sign up at https://nearcut.com/en-GB/sign_up and replace the anchor with `<iframe src="https://iframe-{id}.nearcut.com/">`.
- No build step. `index.html` ships exactly as committed.
