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

- Shared styles for every page, legal pages included: assets/css/site.css.
  Colours, radii and spacing are CSS custom properties at the top of the
  file. Large orange text uses `--accent` (#e2643a); small orange text uses
  `--accent-text` (#b84a25) so it keeps 4.5:1 contrast on white and on the
  beige `--canvas` background.
- Fonts: Inter 4 (SIL Open Font License 1.1, https://github.com/rsms/inter),
  self-hosted from assets/fonts/ as Latin subsets in four weights
  (400, 500, 600, 700). Headlines use Inter Bold with tight letter-spacing.
- Header: the desktop navigation is hidden below 900 px and replaced by a
  native `<details>` menu, so it works without JavaScript.
- assets/js/site.js: the product tour on the home page (keyboard-accessible
  tabs with arrow keys, Home and End; every step stays visible without
  JavaScript) and closing the mobile menu after a link, on Escape or on an
  outside click.
- Images: assets/images/. screens/ holds Cuisy app screens (WebP, 600 px
  wide, plus a `-360.webp` variant for `srcset`); the home page JSON-LD
  links to the 600 px files. brand/ holds the wordmark (cuisy-logo.webp) and
  Pufi, the mascot (pufi.webp, pufi-300.webp). Screens show sample recipes.
  og-cuisy.jpg (1200x630) is the social preview image; cuisy-icon-144.png is
  the favicon.
- Store badges: badges/app-store-badge.svg is Apple's official black
  “Download on the App Store” badge (US-UK English) from
  toolbox.marketingtools.apple.com, and badges/google-play-badge.png is
  Google's official badge from play.google.com with its transparent padding
  trimmed. Download blocks show both at the same height, App Store first. The
  footer carries the Apple and Google trademark lines.
- Store links: the App Store link is the region-neutral
  https://apps.apple.com/app/cuisy-video-to-recipe-saver/id6758858246, so
  visitors land in their own country's store. Play links use the referrer
  `utm_source=getcuisy&utm_medium=website&utm_campaign=<page>`. The home page
  JSON-LD lists Android and iOS, with an offer for each store. Every
  marketing page has the Smart App Banner meta tag (app-id=6758858246).
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
  The privacy policy, terms and account deletion pages use the shared header,
  footer and stylesheet (`.legal-*` classes); edit their wording only on
  purpose, since store listings link to them.
- The home page mentions the roadmap once, under the plans, labelled
  “Planned · not yet released”. Keep any future-feature copy labelled the same
  way.
- Cuisy is live on the App Store (iPhone) and Google Play (Android); the
  App Store listing was confirmed live on November 19, 2026.
- Free/Premium descriptions were checked against the public Google Play
  listing. Recheck them when product limits or availability change.

When adding a page, include a unique title, description, canonical URL,
Open Graph/Twitter tags and the apple-itunes-app meta tag, then add it to
sitemap.xml and the relevant navigation or footer column. Only describe
released features, and never add ratings, reviews or user counts.
