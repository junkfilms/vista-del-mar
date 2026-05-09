# 🌅 vista-del-mar

> *Upcoming anthem film. Air date — October 10, 2026.*

A small, sunlit corner of the internet for the production team. Living timelines, briefs, and notes — published as a tiny static site so anyone with the link can flip through them.

**🌐 Live site:** [junkfilms.github.io/vista-del-mar](https://junkfilms.github.io/vista-del-mar/)

---

## ☕ How this place works

- The front door is `index.html` at the repo root. It lists every shared document as a tappable card.
- Each shared document is its own `.html` file, also at the repo root *(e.g. `vista_del_mar_timeline.html`)*.
- Push to `main` → GitHub Pages quietly redeploys. Usually live within a minute.
- The site is **public**. Anything secret stays in Drive.

---

## ✍️ Adding a new document

Two short steps. Upload the file, then introduce it on the landing page.

### 1 · Upload the HTML file

1. Head over to the repo: [github.com/junkfilms/vista-del-mar](https://github.com/junkfilms/vista-del-mar)
2. Hit **Add file → Upload files** *(or just drag-and-drop into the file list)*.
3. Use a calm, lowercase, underscore-style filename — `casting_brief.html`, `shot_list_v2.html`, that kind of thing.
4. Scroll down, leave a short commit note, and click **Commit changes**.

### 2 · Link it from `index.html`

1. Open `index.html` and click the little pencil to edit.
2. Find the `<ul class="docs">` block. Copy one of the existing `<li>...</li>` blocks and paste a new copy below it.
3. Update the `href`, title, and description. Here's the template:

```html
<li>
  <a href="YOUR_FILE.html">
    <div class="doc-title">Display Title</div>
    <div class="doc-desc">One-line description of what this doc covers.</div>
  </a>
</li>
```

A working example:

```html
<li>
  <a href="casting_brief.html">
    <div class="doc-title">Casting Brief</div>
    <div class="doc-desc">Roles, sides, and audition logistics.</div>
  </a>
</li>
```

4. Commit. Wait a beat, refresh [the site](https://junkfilms.github.io/vista-del-mar/), and your new card is there.

---

## 🧹 Removing or renaming a document

- **Remove** — delete the `.html` file from the repo *and* remove its `<li>` block from `index.html`. Same commit is fine.
- **Rename** — rename the file in the repo, then update the `href` in `index.html` to match.

---

## 🎨 Editing the landing page itself

`index.html` is a single self-contained file. All CSS lives inside a `<style>` block in the `<head>` — no build step, no dependencies. Edit on GitHub or locally; commit to `main`.

A few common tweaks:

- **Accent color** — find `--accent: #e4b363;` in the `:root` block and pick your favorite hex.
- **Subtitle / air date** — look for `<p class="subtitle">` inside `<header>`.
- **A new section** — copy the `<h2>Documents</h2>` + `<ul class="docs">` pattern. You can have as many sections as you'd like *(Pre-production, Production, Post…)*.

---

## 🐛 A small heads-up

GitHub's web editor sometimes auto-completes closing HTML tags and quietly leaves fragments behind, like `</div>div>`. If that happens after a commit:

1. Edit the file again.
2. Select all *(`Cmd/Ctrl + A`)* and delete.
3. Paste your clean HTML from your clipboard — it won't be re-mangled.
4. Commit.

Or, more peacefully: edit `.html` files in your local editor and push. The quirk only lives inside the GitHub web editor.

---

## 🩹 Troubleshooting

- **My new doc 404s.** The `href` in `index.html` must match the actual filename exactly *(case-sensitive, including `.html`)*.
- **Site looks stale.** Pages can take a minute to redeploy; check the **Actions** tab for status, then hard-refresh *(`Cmd/Ctrl + Shift + R`)*.
- **`index.html` is broken.** Open the file's commit history, find the last good commit, and revert. Nothing is permanent here.

---

*Last updated — May 9, 2026*
