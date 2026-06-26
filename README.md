# Inverted Pendulum on a Cart: project page

Source for the project landing page:

> **Nonlinear Swing-Up and Stabilization of Inverted Pendulum on a Cart Using Energy Control Method Based on Multiple Lyapunov Functions, Sliding Mode Control, and Pole Placement**
> Gene Patrick Rible.
> *Preprints.org*, 2024. DOI: [10.20944/preprints202405.1003.v1](https://doi.org/10.20944/preprints202405.1003.v1)

Live at **https://genepatrickrible.github.io/inverted-pendulum/**.

Built as a static page (Bulma, Font Awesome, Academicons via CDN) in the style of the
Nerfies academic project-page template. No build step; the repo serves directly from
GitHub Pages.

## Repository layout

```
inverted-pendulum/
├── index.html              single-page site
├── favicon.ico             cart-pole mark (also at static/images/favicon-*.png)
├── robots.txt              allows all crawlers, points at sitemap
├── sitemap.xml             one-URL sitemap for Search Console
├── static/
│   ├── css/index.css       custom styles on top of Bulma
│   ├── js/index.js         cite dropdown + clipboard + figure lightbox
│   ├── images/             figure PNGs, favicons, teaser, OG image
│   └── videos/             reserved for future local clips
└── .nojekyll               disables Jekyll so static/ serves verbatim
```

## Figures to add

Drop these into `static/images/` with these exact names and the page wires them
automatically (a dashed "Add image: …" box shows until each file exists):

| File | Paper figure |
| ---- | ------------ |
| `teaser.gif` | hero looping swing-up clip (GIF or short MP4 frame export) |
| `fig1-equilibria.png` | Fig. 1: upright / falling / downward equilibria |
| `fig2-schematic.png` | Fig. 2: cart-pole schematic |
| `fig3-energy-zero.png` | Fig. 3: set of states with zero mechanical energy |
| `fig4-swingup-cases.png` | Fig. 4: the two single-Lyapunov failure cases |
| `fig5-phi-angle.png` | Fig. 5: rod angle φ from the downward equilibrium |
| `fig6-results-rest.png` | Fig. 6: responses, swing-up from rest |
| `fig7-results-fastspin.png` | Fig. 7: responses, fast initial spin |
| `fig8-results-far.png` | Fig. 8: responses, far-from-equilibrium start |
| `fig9-flowchart.png` | Fig. 9: optional controller-technique flowchart |

After adding figures, generate the 1200×630 social-preview image:

```bash
python3 ~/.claude/skills/research-page-builder/scripts/make_og_image.py \
  static/images/teaser.gif static/images/teaser-social.png
```

## Preview locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Wired links

| Button | Destination |
| ------ | ----------- |
| Paper (PDF) | https://www.preprints.org/frontend/manuscript/01958f58736242b038e4ed3f64899d48/download_pub |
| DOI | https://doi.org/10.20944/preprints202405.1003.v1 |
| Code | https://github.com/generible/Inverted-Pendulum-Simulator |
| Video | YouTube playlist: **TODO**, search `YOUTUBE_PLAYLIST_URL` in index.html |
| Schedule | https://calendar.app.google/YsaGA9uHTuNJpuD77 |
| Discussion | https://github.com/genepatrickrible/inverted-pendulum/discussions |

## Integrations

- **YouTube movies:** the five supplementary clips embed via
  `https://www.youtube.com/embed/YOUTUBE_ID_MOVIE{1..5}`. Replace each
  `YOUTUBE_ID_MOVIE{n}` token (appears once inline in a result block and once in
  the supplementary-videos grid) with the 11-character video ID. Upload the
  videos **Public** (not Unlisted) so Scholar and video crawlers index them, and
  set `YOUTUBE_PLAYLIST_URL` (two places) to the public playlist.
- **Schedule button:** points at the Google Calendar Appointment Scheduling page
  `https://calendar.app.google/YsaGA9uHTuNJpuD77` (same booking link as the
  fur-wetting and quadcopter-failsafe pages).
- **Giscus comments:** already wired in the `#discussion` section (very bottom)
  for `genepatrickrible/inverted-pendulum`, Announcements category
  (`data-repo-id=R_kgDOTGRcWg`, `data-category-id=DIC_kwDOTGRcWs4C_9IY`,
  `data-mapping=pathname`, `data-loading=lazy`). Discussions are enabled on the
  repo; the widget renders once the **Giscus GitHub App** is installed on this
  repo at https://github.com/apps/giscus.

## SEO

The page ships with:
- Google Scholar `citation_*` meta tags (title, author, date, journal, publisher, DOI, PDF URL).
- A Schema.org `ScholarlyArticle` JSON-LD block.
- Canonical URL, keywords, author, and search-engine verification placeholders
  (`GSC_TOKEN_PLACEHOLDER`, `BING_TOKEN_PLACEHOLDER`).
- A 1200×630 PNG (`teaser-social.png`) for Open Graph and Twitter card previews.
- `sitemap.xml` and `robots.txt` at the repo root.

## Credits

Page template adapted from [Nerfies](https://github.com/nerfies/nerfies.github.io),
used under [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/).
