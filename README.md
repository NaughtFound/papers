# Papers I read

Notes and open discussion on the papers I read, covering generative models, causality, explainability and medical imaging.

Live site: https://naughtfound.github.io/papers/

Each paper has a short write-up, and anyone can join the discussion by signing in with GitHub. Comments are stored in this repo's [Discussions](../../discussions).

## How it works

- `index.html` is the whole site. It is a single static page with no build step.
- `papers/index.json` lists every paper and its details.
- `papers/<slug>.md` holds the notes for each paper, written in Markdown.
- Comments use [giscus](https://giscus.app), which maps each paper to one GitHub Discussion thread.
- `giscus/light.css` and `giscus/dark.css` style the comment box to match the site's light and dark themes.
- `.github/workflows/deploy.yml` checks the JSON and publishes the site to GitHub Pages whenever you push to `main`.

```
index.html
papers/
├── index.json
├── ddpm.md
├── ldm.md
└── gradcam.md
giscus/
├── light.css
└── dark.css
.github/workflows/deploy.yml
```

## Add a paper

1. Write your notes in `papers/<slug>.md`. Start at the `##` headings, because the page already shows the title, authors, links, summary and takeaways.
2. Add an entry to `papers/index.json`:

   ```json
   {
     "slug": "ddpm",
     "title": "Denoising Diffusion Probabilistic Models",
     "authors": "Jonathan Ho, Ajay Jain, Pieter Abbeel",
     "year": 2020,
     "venue": "NeurIPS",
     "arxiv": "2006.11239",
     "code": "https://github.com/hojonathanho/diffusion",
     "tags": ["diffusion", "generative"],
     "added": "2026-09-28",
     "summary": "One or two sentences describing the paper.",
     "takeaways": ["First point.", "Second point."],
     "bodyUrl": "papers/ddpm.md"
   }
   ```

3. Commit and push to `main`. The site updates in a minute or two.

Required fields: `slug`, `title`, `authors`, `year`, `summary`. The rest are optional.

Keep each `slug` unique and don't rename it later, because the discussion thread is tied to it.

## Set up your own copy

1. Create a repo named `papers` and add these files.
2. In Settings, then Pages, set the source to **GitHub Actions**.
3. In Settings, then General, turn on **Discussions**.
4. Install the giscus app on the repo, then get your `repoId` and `categoryId` from [giscus.app](https://giscus.app).
5. Put the repo name and IDs in the `CONFIG` block at the top of the script in `index.html`.

## Preview locally

The page loads its data with `fetch`, so open it through a local server rather than double-clicking the file:

```
python3 -m http.server 8000
```

Then visit http://localhost:8000. Comments only appear on the live site, where giscus can reach the repo.
