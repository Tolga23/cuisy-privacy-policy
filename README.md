# Cuisy official website

Buildless HTML/CSS website with a small progressive JavaScript enhancement for
**https://getcuisy.com**, hosted on GitHub Pages.

## Pages

| URL | File |
| --- | --- |
| / | index.html |
| /features/ | features/index.html |
| /ai/ | ai/index.html |
| /about/ | about/index.html |
| /support/ | support/index.html |
| /video-to-recipe/ | video-to-recipe/index.html |
| /save-recipes-from-tiktok-instagram-youtube/ | save-recipes-from-tiktok-instagram-youtube/index.html |
| /recipe-keeper-app/ | recipe-keeper-app/index.html |
| /privacy-policy.html | privacy-policy.html |
| /terms-of-service.html | terms-of-service.html |
| /delete-account.html | delete-account.html |

The old /support.html address redirects to /support/. The root /index.html
now serves the homepage. Update store support URLs to https://getcuisy.com/support/.

## Publishing

GitHub Pages is configured to deploy the root of **main**. Merge reviewed
changes into main to publish. Keep CNAME set to getcuisy.com and HTTPS enabled
in the repository's Pages settings. No build step or package installation is needed.

Pages runs its standard Jekyll build. Every page is plain HTML without front
matter, so Jekyll copies it byte for byte. `_config.yml` keeps this README off
the public site (`exclude`), turns off the default theme (`theme: null`), and
Jekyll skips dotfiles. Do not add a `.nojekyll` file: it would publish the
README and dotfiles again. List any new internal file under `exclude`.

Serve the repository root with any local static HTTP server to preview.
Root-relative links require HTTP hosting; opening HTML directly as a file
does not reproduce the deployed site.

## Content and assets

- Shared marketing styles: assets/css/site.css.
- Product tour: assets/js/site.js. Keyboard-accessible tabs use arrow keys,
  Home, and End. Every step remains visible when JavaScript is disabled.
- Images: assets/images/. The icon and four promotional screenshots are
  Cuisy's existing artwork from its official Google Play listing:
  https://play.google.com/store/apps/details?id=com.hardal.cuisy
- Screenshots are lossy WebP (quality 80) at 640 px, with 360 px and 540 px
  variants (`-360.webp`, `-540.webp`) for `srcset`. Keep the 640 px file name
  unchanged; structured data links to it. og-cuisy.jpg (1200x630) is the
  social preview image; cuisy-icon-144.png is the in-page and favicon mark.
- Store badges: badges/google-play-badge.png is Google's official badge from
  play.google.com with its transparent padding trimmed. Pages showing it carry
  the Google trademark line in the footer. Play links use the referrer
  `utm_source=getcuisy&utm_medium=website&utm_campaign=<page>`.
- iOS: download blocks show “Coming soon on the App Store” as plain text and
  the home page JSON-LD lists Android only. When the App Store listing is live,
  follow the `iOS`/`TODO(iOS)` comments: swap in Apple's official badge and add
  the App Store offer. Every marketing page already has the Smart App Banner
  meta tag (app-id=6758858246).
- Images are hosted locally; the website loads no third-party scripts,
  fonts, analytics, or embeds.
- Support uses the shared design and a native, JavaScript-free FAQ.
- About and marketing content focus on Cuisy's purpose, features, and product
  direction. Do not add personal creator profiles, names, or Person author
  metadata, or invent a registered company, founding year, funding, or metrics.
- Contact routing: support@getcuisy.com for app/account help,
  hello@getcuisy.com for general enquiries and collaboration, and
  privacy@getcuisy.com for privacy, data access/export, and account deletion.
- The AI page distinguishes released features from the planned Claude API
  integration. It does not claim a live integration, Anthropic endorsement,
  partnership, or acceptance into a startup program. Update the site and
  privacy disclosures to match actual processing before a provider change.
- The product roadmap at /ai/#product-roadmap labels meal planning,
  calorie/macro tracking, and country-specific grocery connections as Planned,
  and coordinated shopping and leftover
  suggestions as Exploring. None are claimed as released or given dates.
  Nutrition totals are planned around food-composition data and editable
  portions; Claude is proposed for recipe interpretation and meal suggestions.
- Grocery connections describe a future transfer to a retailer list or cart,
  with product review before checkout. Countries and retailers remain to be
  confirmed; no integrations, retailer partnerships, or universal coverage
  are claimed. The app's src/i18n/config.ts defines 10 language locales,
  not 10 supported countries; do not infer country coverage from languages.
- Legal terms and retention rules are retained; contact routing is updated.
- Google Play is the active download destination. iOS is marked “coming soon”
  because App Store Connect showed version 1.0.1 waiting for review when checked
  on October 11, 2026. Once publicly available, verify the App Store URL for
  app ID 6758858246 and update the download blocks across the site.
- Free/Premium descriptions were checked against the public Google Play
  listing. Recheck them when product limits or availability change.

When adding a page, include a unique title, description, canonical URL,
Open Graph/Twitter tags and the apple-itunes-app meta tag, then add it to
sitemap.xml and the relevant navigation or footer column. Only describe
released features, and never add ratings, reviews or user counts.
