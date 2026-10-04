# Nicholas Korom

Static personal website for Nicholas Korom, connected to Vercel through pushes to `main`.

Build: `python3 scripts/build.py`

Preview: `python3 -m http.server 8765`

The build generates seven pages, canonical URLs, social metadata, Person/Website/WebPage structured data, robots.txt, sitemap.xml, and llms.txt. The production domain is configured through `SITE_URL`.

## Domain migration

The temporary site is https://www.nickkorom.com. The existing nickkorom.com hosting has not been changed.

Before moving the domain:

1. Connect a replacement media/speaking inquiry form or retain the existing WordPress form on a separate host. The current inquiry links use https://www.nickkorom.com/contact/ and will point back to this static site after a domain move. Update those links in scripts/build.py before changing DNS.
2. Add nickkorom.com and www.nickkorom.com to the existing Vercel project, choose a primary hostname, and apply Vercel's verified DNS instructions while preserving email DNS records.
3. Rebuild with `SITE_URL=https://www.nickkorom.com python3 scripts/build.py` (or the chosen primary hostname), commit and push to main.
4. Verify certificates, the alternate hostname redirect, all seven original routes, inquiry destinations, and the sitemap. Submit the production sitemap in Search Console.
5. Replace references to the temporary hostname after cutover. Review the privacy page against any new inquiry provider or analytics integration.

Content basis: Nick's existing personal site and BNB Accelerator's public company site. Company figures are labeled as company figures; this site makes no guaranteed performance claims. No advertising analytics or visitor-submitted forms are installed in the static site.
