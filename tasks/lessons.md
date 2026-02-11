# Lessons Learned

## Process Preferences
- **Site approval before fetching:** When multiple websites need to be accessed/referenced, always list them first and get user approval before fetching any of them.

## Publishing to Medium with GitHub-hosted Images

### Problem
Medium's "Import a story" feature (`medium.com/p/import`) requires a URL that serves proper `text/html` content. Raw GitHub URLs (`raw.githubusercontent.com`) serve files as `text/plain`, so Medium's importer fails to parse them.

### Solution: GitHub Pages
1. **Make the repo public** (required for both image hosting and GitHub Pages):
   ```bash
   gh repo edit <owner>/<repo> --visibility public
   ```
2. **Enable GitHub Pages** from the master/main branch root:
   ```bash
   gh api repos/<owner>/<repo>/pages -X POST --input - <<'EOF'
   {"source":{"branch":"master","path":"/"}}
   EOF
   ```
3. **Wait ~60 seconds** for the build, then verify:
   ```bash
   gh api repos/<owner>/<repo>/pages
   # status should be "built"
   ```
4. **Import to Medium** using the GitHub Pages URL:
   ```
   https://<owner>.github.io/<repo>/article/medium_ready.html
   ```

### Key Details
- GitHub Pages URL serves proper `text/html` content type, which Medium can parse
- Images in the HTML should use `raw.githubusercontent.com` URLs (these work fine for `<img>` tags — the content-type issue only affects the importer's top-level URL)
- The HTML file should include `<figure>` / `<figcaption>` for image captions — Medium picks these up during import
- After import, add tags and preview image manually in Medium's editor

### Reusable Workflow Files
- `article/medium_ready.html` — HTML formatted for Medium import (semantic HTML, no custom CSS classes)
- `article/medium_draft.md` — Source markdown with GitHub raw image URLs
- `article/PUBLISHING.md` — Step-by-step publishing checklist
