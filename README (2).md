# Ann Arbor Bike Map

A hand-inked, tilted map of Ann Arbor with filmed handlebar rides as clickable routes. It is one static page. No build step, no dependencies.

## Files

- `index.html` is the whole site: markup, styles, map drawing and the clip data.
- `.nojekyll` tells GitHub Pages to serve the files as they are.

## Deploy on GitHub Pages

1. Create a new repository on GitHub, for example `ann-arbor-bike-map`. Public is fine, and it is required for Pages on a free account.
2. Upload `index.html`, `.nojekyll` and `README.md` to the root of the repository. On the repository page, choose Add file, then Upload files.
3. Open Settings, then Pages.
4. Under Build and deployment, set Source to "Deploy from a branch". Pick the `main` branch and the `/ (root)` folder, then Save.
5. Wait a minute or two. The site appears at `https://YOUR-USERNAME.github.io/ann-arbor-bike-map/`.

To use your own domain, add it under Settings, then Pages, then Custom domain, and point a CNAME record at `YOUR-USERNAME.github.io`.

## Updating the clips

The rides live in one array named `C` near the top of the first `<script>` in `index.html`. Each row is:

`[id, street, from, to, direction, infrastructure, quality, duration, hover text, note, neighborhood, YouTube video ID, route points]`

- The YouTube video ID is the part of the Shorts link after `/shorts/` and before any `?`.
- Infrastructure is one of `protected`, `painted`, `sharrow`, `shared`, `trail`, `gravel`, `sidewalk`, `other`.
- Hover text is the short line shown on hover. Leave it empty to fall back to the street and cross streets.
- A row with an empty video ID draws as a dashed gray "not uploaded yet" route.
- Route points are `[east, south]` positions on the hand-placed street grid. They are approximate and will move once the roads are redrawn.

Commit the change on GitHub and Pages republishes in about a minute.

## Notes

- The highways and river were traced by eye from a screenshot of a map of Ann Arbor. They are an illustration, not survey data.
- Fonts (Figtree and Young Serif) load from Google Fonts. If they fail to load, the page falls back to the system serif and sans-serif.
- Videos play inside the side panel through YouTube's embed player. If one shows "video unavailable", open it in YouTube Studio, go to Details, then Show more, and turn on Allow embedding. Unlisted videos embed fine.
