# Publishing Workflow

Follow these steps when you're ready to publish the Medium article.

---

## 1. Set Up Personal Access Token (one-time)

1. Go to **GitHub Settings** > **Developer settings** > **Personal access tokens** > **Fine-grained tokens**
2. Click **Generate new token**
3. Set the token name (e.g. `repo-visibility-toggle`)
4. Under **Repository access**, select **Only select repositories** > `ghighcove/superbowl_seat_prices`
5. Under **Permissions** > **Repository permissions**, set **Administration** to **Read and write**
6. Generate the token and copy it
7. Go to the repo's **Settings** > **Secrets and variables** > **Actions**
8. Add a new secret named `REPO_VISIBILITY_TOKEN` with the token value

## 2. Make the Repository Public

**Option A — GitHub Actions (recommended):**
1. Go to the repo's **Actions** tab
2. Select **Make Repository Public** in the left sidebar
3. Click **Run workflow** > **Run workflow**
4. Wait for the green checkmark confirming success

**Option B — CLI:**
```bash
gh repo edit ghighcove/superbowl_seat_prices --visibility public
```

**Option C — Manual:**
1. Go to repo **Settings** > **General** > scroll to **Danger Zone**
2. Click **Change repository visibility** > set to **Public**

## 3. Verify Images Load

After the repo is public, confirm the chart images render by opening any of these URLs:
- https://raw.githubusercontent.com/ghighcove/superbowl_seat_prices/master/exports/trend_nominal_vs_adjusted.png
- https://raw.githubusercontent.com/ghighcove/superbowl_seat_prices/master/exports/face_vs_resale.png

If they show the charts, the article images will work on Medium.

## 4. Publish to Medium

**Option A — Import (fastest):**
1. Go to [medium.com/p/import](https://medium.com/p/import)
2. Paste the raw URL of `medium_ready.html` from the public repo, or upload the local file
3. Review formatting in Medium's editor

**Option B — Copy-paste:**
1. Open a new story on Medium
2. Copy article text section by section from `medium_draft.md`
3. For each image: drag-and-drop the corresponding PNG from `exports/` into the editor
4. Add image captions (the italic text below each image in the draft)

## 5. Review & Finalize

- Check all 6 images render correctly
- Verify all links work (GitHub repo, LinkedIn profile)
- Add Medium tags: **Super Bowl**, **Data Visualization**, **Sports Analytics**, **NFL**, **Inflation**
- Set a preview image (recommended: `trend_nominal_vs_adjusted.png`)
- Publish or schedule

---

## File Reference

| File | Purpose |
|------|---------|
| `article/medium_draft.md` | Source markdown with GitHub raw image URLs |
| `article/medium_ready.html` | HTML version for Medium's import feature |
| `exports/*.png` | 6 chart images to include in the article |
| `.github/workflows/make-public.yml` | One-click workflow to make repo public |
