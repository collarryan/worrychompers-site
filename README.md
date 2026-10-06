# worrychompers.com

The website for Worry Chompers: one static page, no build step, no JavaScript, no cookies and no
analytics. `index.html` and `styles.css` are the whole of it.

Everything on it comes from the app (`collarryan/worry-muncher`), so it looks like the app:

- **The meadow** is the app's own Scene (`src/components/Scene/Scene.tsx`) redrawn as SVG: the
  same sky, sun, clouds, trees, bush, grass and flowers, in the same colours. The characters stand
  in the page flow and the grass is laid out up from their feet (`--below`, `--behind` in
  `styles.css`), so nothing can overlap them at any width.
- **Pictures** (`img/`, converted to WebP): the logo is `store/art/Worry-Chomper-Logo.svg`, the hero
  is `store/art/splash-artwork.png`, the four step and group pictures are `assets/onboarding/`, the
  tile icons `assets/tiles/` and the grown-ups icons `assets/icons/`. `meet.webp` is the one
  changed: its shadows were grey for the cream welcome card and are recoloured to the meadow's
  shadow (`#4A6E33` at 35%), only where they touch the grass.
- **Fonts**: Nunito (SIL OFL, `fonts/Nunito-OFL.txt`), subset to Latin as WOFF2 from the app's
  `assets/fonts` with fontTools.
- **House style**: British English, curly apostrophes, no em dashes, no health claims, and every
  claim checked against the app as it ships.
- **Words** on the home page are Ryan's newer ones: the store screenshot captions
  (`store/screenshots/`) first, then the app's own pages (About & privacy, Worry settings, Worry
  Time, the first welcome card). `STORE_LISTING.md` is older and was not used.
- **`support/` and `privacy/` are the only home of those pages** (since 6 October 2026), moved
  here from `crooked.app/worry-chompers/`. The old addresses there, and the original
  `collarryan.github.io/worry-chompers-privacy`, forward here. The app links to `privacy/`
  (`POLICY_URL` in the app's `app/parent/about.tsx`), whose "Last updated" line must match
  `LAST_UPDATED` in that file word for word. The contact is hello@worrychompers.com.
- **The footer carries Crooked Ltd's registered details** on every page, which a UK company's
  website has to show.
- `og.png` is the picture shown when the link is shared (1200 x 630).
- **Until launch the page says "Coming soon to Google Play and the App Store"** (twice: the top and
  Meet the Chompers), so nobody lands on a listing that does not exist yet. **On launch day** put
  Google's official badge back in both places - `img/google-play-badge.png`, unaltered, linking to
  `https://play.google.com/store/apps/details?id=com.worrychompers.app` - and say "Coming soon to
  iPhone" beside it. The trademark line the badge requires is already in the footer. No Apple badge
  until the app is on the App Store: Apple does not allow one before.
