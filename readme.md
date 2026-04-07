# ALMA Web-based OT Tutorial — Developer Notes

For guidance and reproducibility

## Repository structure

```
.
├── _config.yml              # Jekyll configuration (theme, callouts, metadata)
├── index.md                 # Home page
├── docs/                    # Tutorial sections (one .md per section)
│   ├── 01_introduction.md
│   ├── 02_proposal-info.md
│   ├── ...
│   └── 11-differences-workarounds.md
└── readme.md                # This file (excluded from build)
```

## Deploying to GitHub Pages

### 1. Create the GitHub repo (if not already done)

```bash
gh repo create YOUR-USERNAME/alma-ot-tutorial --public --source=. --push
```

Or manually:

```bash
git remote add origin git@github.com:YOUR-USERNAME/alma-ot-tutorial.git
git push -u origin main
```

### 2. Enable GitHub Pages

Go to the repo on GitHub → **Settings** → **Pages** → set:

- **Source**: "Deploy from a branch"
- **Branch**: `main`, folder `/` (root)
- Click **Save**

The site will be live at `https://YOUR-USERNAME.github.io/alma-ot-tutorial/`
within a few minutes.

### 3. Set `baseurl` in `_config.yml`

If your repo is named `alma-ot-tutorial`, set:

```yaml
baseurl: "/alma-ot-tutorial"
url: "https://YOUR-USERNAME.github.io"
```

If you deploy to `YOUR-USERNAME.github.io` (the root user site), leave
`baseurl` empty.

## Local preview

### Option A: grip (quick, no Ruby needed)

```bash
pip install grip
grip index.md
# open http://localhost:6419
```

**Limitations:** grip does not render `just-the-docs` callout syntax
(`{: .tip }`, `{: .warning }`, etc.) or the theme layout. It only
previews raw GitHub-flavoured Markdown.

### Option B: Full Jekyll build (exact GitHub Pages rendering)

Requires Ruby ≥ 2.7:

```bash
gem install bundler
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```

This renders the site exactly as GitHub Pages will.

## Callout syntax (just-the-docs)

The theme supports styled callout boxes. Place the class annotation
**on the line immediately before** the paragraph:

```markdown
{: .tip }
This is a tip — rendered in a green box.

{: .warning }
This is a warning — rendered in a yellow box.

{: .important }
This is important — rendered in a red box.

{: .note }
This is a note — rendered in a blue box.

{: .new }
This is new in Cycle 13 — rendered in a purple box.
```

Multi-line callouts use the `>` blockquote syntax:

```markdown
{: .warning }
> This is a multi-line warning.
>
> It can contain **bold**, `code`, and other Markdown formatting.
> It can also span multiple paragraphs.
```

The callout types (`tip`, `note`, `warning`, `important`, `new`) are
defined in `_config.yml` under the `callouts:` key. You can add more.

## Adding a new section

1. Create a new `.md` file in `docs/`.
2. Add front matter with `title`, `layout: default`, and `nav_order`.
3. The sidebar navigation is generated automatically from the front matter.

```markdown
---
title: My New Section
layout: default
nav_order: 13
---

# My New Section

Content goes here.
```

## Adding images

Place images in an `assets/images/` directory and reference them:

```markdown
![Description](assets/images/my-screenshot.png)
```

For the screenshots from the OT demo, consider creating subdirectories
per section (e.g. `assets/images/spectral-setup/`).

## Useful references

- [just-the-docs documentation](https://just-the-docs.com/)
- [GitHub Pages documentation](https://docs.github.com/en/pages)
- [ALMA OT User Manual](https://almascience.eso.org/proposing/observing-tool)
- [ALMA OT FAQ and Known Issues](https://almascience.eso.org/proposing/observing-tool/faq-and-known-issues)
