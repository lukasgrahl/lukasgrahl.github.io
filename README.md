# Lukas A. Grahl — Quarto website

A small, maintainable academic website built with Quarto and hosted with GitHub Pages.

## What is included

- A responsive home page with portrait and short biography
- Research, CV, and photography pages
- A deliberately small CSS file for the visual design
- Automatic publishing through GitHub Actions
- Existing public portrait and photography assets migrated from the previous site

## One-time setup

### 1. Install the tools

Install:

- Quarto: https://quarto.org/docs/get-started/
- Git: https://git-scm.com/downloads
- Visual Studio Code: https://code.visualstudio.com/
- The Quarto extension in Visual Studio Code

### 2. Back up the current repository

Before replacing the current site, clone it and make a backup branch:

```bash
git clone https://github.com/lukasgrahl/lukasgrahl.github.io.git
cd lukasgrahl.github.io
git switch -c old-jekyll-site
git push -u origin old-jekyll-site
```

Return to the publishing branch, which is currently likely to be `master`:

```bash
git switch master
```

### 3. Replace the old source

Copy the contents of this folder into the repository root. Remove the old Jekyll files and folders, but keep any personal files you still need.

Check the result:

```bash
git status
```

### 4. Enable GitHub Actions publishing

In the repository on GitHub, open:

**Settings → Pages → Build and deployment → Source → GitHub Actions**

This is a one-time setting. The workflow in `.github/workflows/publish.yml` will then render and deploy the website whenever you push to `master` or `main`.

### 5. Preview locally

From the repository folder, run:

```bash
quarto preview
```

A browser window will open. The preview refreshes when source files change.

### 6. Commit and publish

```bash
git add .
git commit -m "Replace Jekyll site with Quarto site"
git push
```

The GitHub Actions tab will show the deployment. The public address remains:

https://lukasgrahl.github.io/

## Routine updates

Most updates require editing only one file:

| Content | File |
|---|---|
| Home page and biography | `index.qmd` |
| Research and papers | `research.qmd` |
| Web CV | `cv.qmd` |
| Photography gallery | `photography.qmd` |
| Colours, spacing, and type | `styles.css` |
| Navigation | `_quarto.yml` |

The normal workflow is:

```bash
quarto preview
git add .
git commit -m "Update research page"
git push
```

## Adding a PDF CV

The current site contained a PDF CV, but this package does not overwrite it with an assumed or potentially outdated document.

1. Copy your current PDF to `files/cv.pdf`.
2. Open `cv.qmd`.
3. Uncomment the download-button line near the top.

## Adding a research paper

1. Put the paper in `files/`, for example `files/my-paper.pdf`.
2. Open `research.qmd`.
3. Copy the commented paper template and replace its title, coauthors, description, and links.

## Adding photographs

See `images/photography/README.md`. Each new photograph requires one short `<figure>` block in `photography.qmd`.

## Design choices

The site intentionally avoids a blog, search, automatic publication databases, dark-mode logic, JavaScript galleries, and external font dependencies. It uses system fonts and a small amount of CSS, which keeps maintenance and failure points to a minimum.
