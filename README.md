# SINCS Lab Website

Source for the Sustainable Industrial-Natural Coupled Systems (SINCS) Lab
site, built with Jekyll and hosted on GitHub Pages.

## How it works

Content lives in data, not code:
- **Lab info, members, URLs** → edit `_config.yml`
- **Each project** → one file in `_projects/`
- **Design** → `assets/style.css`; shared shell in `_layouts/`

Editing `_config.yml` or a project file and committing redeploys the site
automatically.

## Editing common things

**Add a lab member:** add an entry to the `members:` list in `_config.yml`
with `group` (pi/postdoc/phd) and `status` (current/past). To graduate
someone, change `status` to `past` and add `now: "Destination"`.

**Add a project:** copy `_projects/_TEMPLATE.md` to a new name (e.g.
`_projects/nitrogen-model.md`), fill it in, and set `published: true`.
A card appears on the landing page and a full page generates automatically.

**Update lab mission / about text:** edit the paragraphs in `index.html`.

## Deploying (GitHub Pages)

1. Push this repo to GitHub (public repo, or private with an eligible plan).
2. Settings → Pages → Source: "Deploy from a branch" → `main` / root → Save.
3. In `_config.yml`, set:
   - Free URL: `url: "https://USERNAME.github.io"`, `baseurl: "/REPO-NAME"`
   - Custom domain: `url: "https://yourdomain.org"`, `baseurl: ""`
4. The live URL appears in the Pages settings panel after ~1-2 minutes.

## Security notes

- **Never commit secrets** (API keys, passwords, tokens). The `.gitignore`
  blocks common secret files, but stay alert — anything committed to a
  public repo (even later deleted) may persist in history.
- This site only links *out* to tools; logins happen on those external
  systems, so no credentials live here. Keep it that way.
- For VS Code, install only verified-publisher extensions.

## Custom domain (recommended for long-term NSF use)

Add a file named `CNAME` containing just your domain (e.g. `sincslab.org`),
then set the DNS records GitHub provides. The published URL then stays
stable even if hosting changes — important for links cited in NSF reports.
