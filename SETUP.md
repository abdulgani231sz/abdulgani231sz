# Setup Guide — Advanced Features

Your README now includes two things that need GitHub Actions to run once before they'll show up (they'll be broken/blank images until then):

1. **🐍 Contribution Snake** — an animated snake that "eats" your contribution graph
2. **📊 Metrics Dashboard** — an auto-updating, fully customized stats image (`metrics.svg`)

## One-time setup (2 minutes)

1. Push all these files (`README.md`, `assets/`, `.github/workflows/`) to your `abdulgani231sz/abdulgani231sz` repo.
2. Go to your repo → **Settings → Actions → General**
3. Scroll to **Workflow permissions** → select **"Read and write permissions"** → Save.
   *(Without this, the Actions can't push the generated images back to your repo.)*
4. Go to the **Actions** tab of your repo → you should see "Generate Snake Animation" and "Generate Metrics Dashboard" listed.
5. Click into each one → click **"Run workflow"** (top right) → **Run workflow** button to trigger it manually the first time.
6. Wait ~1–2 minutes for each to finish (green checkmark).
7. Refresh your profile page — the snake and metrics dashboard should now render.

After this first manual run, both workflows are scheduled to auto-refresh once a day on their own — no more manual steps needed.

## If the snake doesn't appear

The snake workflow pushes its output to a branch called `output`. Make sure that branch was created (check the branch dropdown on your repo after the workflow runs). If GitHub Pages isn't needed here — the raw SVG URL in the README pulls directly from that branch, so no Pages setup is required.

## If metrics.svg doesn't appear

Same idea — check that the `metrics.yml` workflow run finished successfully (click into it in the Actions tab to see logs if it failed). The most common failure is step 3 above (workflow permissions) not being set.
