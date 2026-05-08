# portfolio-barbershop-demo

Single-file static portfolio demo for GrantOps Consulting's homepage `ProjectsGrid`. Brand: **Trongate Barber Co.** — fictional modern Glasgow barbershop. Ships a fully custom in-page booker (4-step service → barber → time → details → confirmation), styled to match the cordovan/walnut palette, no third-party booking dependency.

Deployed to `barbershop-demo.grantopsconsulting.com` via GitHub Actions OIDC on push to `main`. Infrastructure (S3 + Cloudflare DNS) lives in `GrantOps-Consulting/grantops-web-infra` under client slug `portfolio-barbershop-demo`.

## Notes

- `<meta name="robots" content="noindex, nofollow">` — only intended path is the curated link from grantopsconsulting.com.
- Footer carries: *Portfolio demo by GrantOps Consulting — no real business sits at this address. View our work at [grantopsconsulting.com](https://grantopsconsulting.com/).*
- All "Book a Chair" CTAs (hero + topbar + nav + per-barber links) point at `#book`, which scrolls to the in-page booker. The booker is purely visual — it generates a fake `TBC-####` reference and does not transact.
- For a real-client engagement, the booker block (`<div class="booker" id="booker">` + the `renderBooker()` JS state machine) is the swap point: replace it with whatever booking platform the client actually uses (Booksy widget, Nearcut/Fresha link-out, Square Appointments, custom backend, etc.). Brief survey of the UK options, current as of May 2026: Booksy is the only one of Booksy/Nearcut/Fresha with a true inline embed (others are copy-paste hyperlinks).
- No build step. `index.html` ships exactly as committed.
