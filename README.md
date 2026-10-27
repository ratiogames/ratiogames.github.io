# ratiogames.github.io

Static site for Ratio Games: studio landing page, Pixel Strategies privacy policy (EN + TR) and `app-ads.txt`.
Plain HTML + one `style.css`; no JavaScript, no trackers.

## Publish (GitHub Pages)

1. Create the GitHub organization `ratiogames`.
2. In it, create a public repo named exactly `ratiogames.github.io`.
3. Push the contents of this folder (including the empty `.nojekyll`) to the `main` branch, at the repo root.
4. Repo Settings -> Pages -> Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
5. After a minute the site is live at https://ratiogames.github.io/
   - Privacy policy URL for the Play Console: https://ratiogames.github.io/pixel-strategies/privacy.html
   - app-ads.txt: https://ratiogames.github.io/app-ads.txt (AdMob crawls it at the root of the developer website;
     set https://ratiogames.github.io as the "Website" in the Play Console store listing).

## Placeholders to fill

| Placeholder | Where |
|---|---|
| Contact email (now `ratiogamestudio@gmail.com`; done) | `index.html` (1x, mailto + text); `pixel-strategies/privacy.html` (sections 1, 10, 13, each mailto + text); `pixel-strategies/privacy-tr.html` (sections 1, 10, 13, each mailto + text) |
| AdMob publisher id (now `pub-4253580448615568`; done) | `app-ads.txt` |
| Google Play link (live once the app is published) | `index.html` (button URL `https://play.google.com/store/apps/details?id=com.ratiogames.pixelstrategies`; remove the "Coming soon" badge and the "(coming soon)" button text) |
| Effective date `2026-10-26` | `pixel-strategies/privacy.html` and `pixel-strategies/privacy-tr.html` (header) |

Replace the email everywhere in one go:

```bash
grep -rl 'ratiogames.contact@gmail.com' . | xargs sed -i '' 's/ratiogames.contact@gmail.com/NEW@ADDRESS/g'
```

## Notes

- `privacy-tr.html` is a machine translation: have a native speaker review it before publishing.
- Keep the policy in sync with the game: re-check it whenever an SDK is added (analytics, crash reporting, another
  ad network, Unity Gaming Services) or the in-game "Settings -> Purchases & privacy -> Privacy options" path changes.
