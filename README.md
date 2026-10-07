# worrychompers.com

The website for Worry Chompers: a home page plus Support and the privacy policy, no build step, no
JavaScript bar the menu's few lines (they slide the pinned bar in once the hero has scrolled away),
no cookies and no analytics. **The three pages share their pieces as copies** - the
meadow drawings (the hidden `<svg>` of symbols), the store badges with the line-up, and the footer -
so a change to one of those goes into all three. **The inner pages follow the reference site's
inner pages**: a compact header with everything centred (small logo linking home, title, one
line; Support's email button sits in it) and the trees framing it, then the content at once -
the policy is a card laid over the bottom of the meadow (`.doc-band`). The menu is Home, Support and Privacy policy only: clear on the sky at the top of each page, and
a pinned bar with the logo once the hero has scrolled away (a fuller opaque bar that was always
there was tried first and taken out: Ryan found it made the site look weird).

Everything on it comes from the app (`collarryan/worry-muncher`), so it looks like the app:

- **The meadow** is the app's own Scene (`src/components/Scene/Scene.tsx`) redrawn as SVG: the
  same sky, sun, clouds, trees, bush, grass and flowers, in the same colours. It runs as a strip
  under the hero and as the hill the Chompers stand on at the bottom; wavy edges are kept to those
  two places on purpose.
- **Pictures** (`img/`): the logo is `store/art/Worry-Chomper-Logo.svg`; the step and builder
  pictures are `assets/onboarding/` (WebP); the tile icons `assets/tiles/` and the grown-ups icons
  `assets/icons/`. `chomper-rest.svg` (the Chomper at rest, its normal smile) is drawn by the
  app's own renderer, `buildFullSVG` in `parts.ts`.
- **Two pictures began as stand-ins, and Ryan kept them** (6 October 2026). If either is ever
  redrawn, keep the file name and shape and nothing else needs to change:
  - `hero-device.webp` (640 x 1284, transparent): the phone with the Home screen, cut from the
    first store screenshot (`store/screenshots/play/01-hero.png`).
  - `lineup.svg` (a wide strip, about 4.5 : 1, transparent): Ryan's own line-up of six
    Chompers on their shadows (uploaded 6 October), its frame cropped to the drawing so the
    lowest shadow is the bottom edge - that is what lets `.gang` stand it on the grass with a
    plain `margin-bottom: var(--below)`. A replacement needs the same crop (no empty space
    above the hats or under the shadows), or the badges float and the shadows sit above the
    grass; if its shape changes, update the `width`/`height` on its `<img>` too.
- **Fonts**: Nunito (SIL OFL, `fonts/Nunito-OFL.txt`), subset to Latin as WOFF2 from the app's
  `assets/fonts` with fontTools.
- **House style**: British English, curly apostrophes, no em dashes, no health claims, and every
  claim checked against the app as it ships.
- **Words** on the home page are Ryan's newer ones: the store screenshot captions
  (`store/screenshots/`) first, then the app's own pages (About & privacy, Worry settings, Worry
  Time, the first welcome card).
- **`support/` and `privacy/` are the only home of those pages** (since 6 October 2026), moved
  here from `crooked.app/worry-chompers/`. The old addresses there, and the original
  `collarryan.github.io/worry-chompers-privacy`, forward here. The app links to `privacy/`
  (`POLICY_URL` in the app's `app/parent/about.tsx`), whose "Last updated" line must match
  `LAST_UPDATED` in that file word for word. The contact is hello@worrychompers.com.
- **Page links are the clean addresses** - `/`, `/support/`, `/privacy/` - never `index.html`
  (Ryan, 7 October 2026: the address bar should read neatly). GitHub Pages serves each
  folder's `index.html` at its folder's address. They are root-relative, so they work on the
  live site but not between files opened straight from disk; pictures, fonts and styles are
  still relative, so a page opened from disk still looks right.
- **Crooked Ltd's registered details are on the privacy page**, under "Who we are". UK law wants
  a company's name, number, place of registration and registered office on its website, not on
  every page, so the footer stays short. Keep them on that page.
- `og.png` is the picture shown when the link is shared (1200 x 630): the hero, flattened.
- **The store badges link to `#` until the listings exist** (twice: in the hero and above the
  line-up), Ryan's call. On launch day, point the Google Play one at
  `https://play.google.com/store/apps/details?id=com.worrychompers.app` and the App Store one at
  the app's App Store page. Both are the stores' official files, unaltered:
  `img/google-play-badge.png` is Google's PNG with only its transparent margin trimmed (so both
  badges share one height), and `img/app-store-badge.svg` comes from Apple's marketing toolbox.
  Apple's rules allow its badge only for an app that is on the App Store, so the iPhone one should
  not stay up long before that. Google's current guidelines ask for no trademark line.
