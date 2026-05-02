# Ian Hinkley Playlists

A static, GitHub-Pages-deployable web app for editorial playlist liner notes.

## Local preview

From this directory:

```sh
python3 -m http.server 8000
```

…then visit <http://localhost:8000/>.

## Folder layout

```
.
├── index.html                                      # Home page (playlist tiles)
├── playlists/
│   └── 30-greatest-living-american-songwriters/
│       └── index.html                              # Detail page
├── assets/
│   ├── styles.css                                  # Shared styles
│   └── covers/
│       └── 30-greatest-living-american-songwriters.svg
└── README.md
```

## Deploying to GitHub Pages

1. Create a new GitHub repo (e.g. `ian-hinkley-playlists`).
2. Copy the contents of this folder into the repo root and push.
3. In **Settings → Pages**, set the source to **`main` branch / `/ (root)`**.
4. Your site will be live at `https://<user>.github.io/<repo>/` within ~1 min.

For a custom domain:

1. Add a `CNAME` file at the repo root containing your domain.
2. In Settings → Pages, fill in the same custom domain.
3. Add a `CNAME` DNS record pointing your domain to `<user>.github.io`.

## Adding a new playlist

1. Create a new folder `playlists/<slug>/` and add an `index.html` modeled on the existing detail page.
2. Add a square cover SVG at `assets/covers/<slug>.svg`.
3. Append a new tile entry in `index.html` pointing to the new detail page.
4. Commit + push.

## What's on the page

- **Home** — title, hero, and a tile for each playlist (cover art, title, month, one-line description).
- **Detail** — playlist cover, "Open in Spotify" CTA, three nested overviews (1 sentence / 3 sentences / full pitch), interactive tracklist (track #, title, artist, album, songwriter, duration, Spotify track link, copy-deep-link), and 2-column songwriter cards (name, Last.fm + Spotify links, 3-sentence description, influences, similar artists, scene).
