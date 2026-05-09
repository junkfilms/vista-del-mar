# vista-del-mar

Upcoming anthem film. Air date: October 10, 2026.

This repository hosts a small static site of working documents (timelines, briefs, etc.) for the production team. The site is served by **GitHub Pages** from the `main` branch and is publicly viewable.

**Live site:** https://junkfilms.github.io/vista-del-mar/

---

## How the site works

- The landing page is `index.html` at the repo root. It lists every shared document as a clickable card.
- Each shared document is its own `.html` file at the repo root (e.g. `vista_del_mar_timeline.html`).
- Whenever you push a change to `main`, GitHub Pages redeploys automatically (usually within ~1 minute).
- Anyone with the link can view the site. Do not put confidential material here.

---

## Adding a new document

There are two steps: (1) upload the HTML file, (2) link it from `index.html`.

### 1. Upload the HTML file

1. Go to the repo: https://github.com/junkfilms/vista-del-mar
2. Click **Add file → Upload files** (or drag-drop into the file list).
3. Add your `.html` file. Use a short, lowercase, underscore-separated filename, e.g. `casting_brief.html`.
4. Scroll down, write a short commit message, and click **Commit changes**.

### 2. Link it from `index.html`

1. Open `index.html` in the repo and click the pencil icon to edit.
2. Find the `<ul class="docs">` block. Inside it, copy the existing `<li>...</li>` block and paste a new copy below it.
3. Update the `href`, title, and description to match your new file. Template:

```html
<li>
  <a href="YOUR_FILE.html">
    <div class="doc-title">Display Title</div>
    <div class="doc-desc">One-line description of what this doc covers.</div>
  </a>
</li>
```

Concrete example:

```html
<li>
  <a href="casting_brief.html">
    <div class="doc-title">Casting Brief</div>
    <div class="doc-desc">Roles, sides, and audition logistics.</div>
  </a>
</li>
```

4. Commit the change. Wait ~1 minute and refresh https://junkfilms.github.io/vista-del-mar/ to see your new card.

---

## Removing or renaming a document

- **Remove:** delete the `.html` file from the repo and remove its `<li>` block from `index.html`. Commit both changes (can be in the same commit).
- **Rename:** rename the file in the repo, then update the `href` in `index.html` to match.

---

## Editing the landing page itself

`index.html` is a single self-contained file — all CSS lives inside a `<style>` block in the `<head>`. There is no build step. Edit it directly on GitHub or locally and commit to `main`.

Common tweaks:

- **Change accent color:** find `--accent: #e4b363;` in the `:root` CSS block and change the hex value.
- **Change the subtitle / air date:** find the `<p class="subtitle">` line in `<header>`.
- **Add a new section:** copy the `<h2>Documents</h2>` + `<ul class="docs">` pattern; you can have multiple sections (e.g. "Pre-production", "Post").

---

## Heads-up: GitHub web editor quirk

When editing HTML directly in GitHub's web editor, it sometimes auto-completes closing tags and produces fragments like `</div>div>`. If you notice this after a commit, the safest fix is to:

1. Edit the file again.
2. Select all (`Cmd/Ctrl+A`), delete.
3. Paste your clean HTML from your clipboard (where it won't be re-mangled).
4. Commit.

Alternatively, edit `.html` files in your local editor and push — that avoids the issue entirely.

---

## Troubleshooting

- **My new doc 404s.** Confirm the filename in `index.html`'s `href` exactly matches the file in the repo (case-sensitive, including `.html`).
- **Site looks stale.** GitHub Pages can take a minute to redeploy. You can check deploy status under the repo's **Actions** tab. Hard-refresh your browser (`Cmd/Ctrl+Shift+R`).
- **I broke `index.html`.** Open the repo's commit history for that file, find the last good commit, and revert.
