# 32 Geerings Road, Martinsville — Landing Page

Long-form, lead-gen landing page for Meta ads traffic. Same static HTML/CSS/JS build as [9 Apanie Close, Summerland Point](../9-apanie-close-summerland-point/) — same navy `#14355c` / sky-blue accent `#89cff0` / cream `#f4f7fb` design system, same Crimson Text + Nunito Sans fonts, same lead-capture modal, same `<base href>` proxy technique.

## Address correction

Your message said "Cooranbong" — the listing copy (`Property ads/32-Geerings-Road-Martinsville.md`), the agency agreement, and the Dropbox folder name all consistently say **Martinsville** (with "Cooranbong, 6 minutes away" listed as a nearby town in the copy itself). This page uses Martinsville. Flag it if that's wrong.

## What's here

- `index.html` — hero, story, 3 feature spotlights (acreage/privacy, vaulted living + fireplace, master suite + character bathroom), 8-photo gallery + lightbox, location/lifestyle section, features-at-a-glance, floorplan, agent block, final CTA, footer, lead-capture modal.
- `images/` — 15 photos selected and compressed from `~/Library/CloudStorage/Dropbox/32 Geerings Road EDITED/WEB/`, plus the most recent floorplan (`32Geerings_floorplan4.jpg`, the 4th and newest of four versions in the folder, dated Aug 31 vs. Aug 26–28 for the others).

## Contact number

This page uses **0478 025 573** throughout (nav, hero, agent section, final CTA), not the usual 02 4314 8086 office line — that's the direct mobile number in the listing copy's own sign-off block, so it's used deliberately, not a mistake.

## Deployment status

Not yet deployed — build it, then deploy the same way as 9 Apanie Close:
1. Push to a new GitHub repo (e.g. `32-geerings-road-martinsville`).
2. Deploy to Vercel under the `myagency` team.
3. Add a rewrite in `my-agency-primary-website`'s `next.config.mjs`:
   ```js
   { source: '/32-geerings-road-martinsville-landing-page/:path*', destination: 'https://32-geerings-road-martinsville.vercel.app/:path*' }
   ```
   No redirect or `skipTrailingSlashRedirect` needed — the page's own `<base href>` already handles relative asset resolution regardless of trailing slash. (An earlier attempt at the Apanie Close page tried a redirect + `skipTrailingSlashRedirect` first and hit an infinite loop; don't repeat that — this `<base href>`-only approach is the proven fix.)
4. Redeploy `my-agency-primary-website` to production.
5. Live URL: `https://myagency.com.au/32-geerings-road-martinsville-landing-page`

## Lead flow

Same Zapier webhook as the other two landing pages (`https://hooks.zapier.com/hooks/catch/22198805/uv0ryfj/`), tagged `32 Geerings Road Enquiry`. Same caveats apply: Slack is confirmed live and working (tested via the Zapier MCP connector on the Apanie Close build); GHL (LeadConnector) and the Dialer connections showed broken access tokens last checked and were deprioritized by the client; Rex CRM has no Zapier connection at all.

## Not included (nothing was supplied)

- Price guide — not shown anywhere on the page.
- Specific inspection times — shown as "Contact Agent" throughout, consistent with the Apanie Close page.
