# 🚀 Publish your aura profile — prodev2025

Your special profile README only shows up if it lives in a **public repo named exactly `prodev2025`** (same as your username). Here's the fast path.

## Option A — push this folder (fastest)

These files are already prepared in `C:\Users\lasha\prodev2025`. From that folder:

```bash
# 1. Create the repo on GitHub first (public, name = prodev2025), do NOT add a README.
#    https://github.com/new   ->  Repository name: prodev2025  ->  Public  ->  Create

# 2. Then push this folder to it:
cd ~/prodev2025
git add .
git commit -m "feat: neon aura profile"
git branch -M main
git remote add origin https://github.com/prodev2025/prodev2025.git
git push -u origin main
```

> The first push may ask you to log in. If it hangs, run it yourself in this session with:
> `! git -C ~/prodev2025 push -u origin main`

## Option B — paste in the web UI

1. Create the repo (public, name `prodev2025`, **tick** "Add a README file").
2. Open `README.md` → pencil icon → delete everything → paste the contents of this folder's `README.md` → Commit.
3. Add file → name it `.github/workflows/snake.yml` → paste this folder's `snake.yml` → Commit.

## Turn on the snake animation (one-time)

1. Repo → **Actions** tab → if prompted, click *"I understand my workflows, enable them"*.
2. Left sidebar → **Generate Snake** → **Run workflow** → **Run**. Wait ~1 min.
3. This creates an `output` branch with `github-snake.svg` / `github-snake-dark.svg`.
4. Verify: open <https://raw.githubusercontent.com/prodev2025/prodev2025/output/github-snake.svg> — if it loads, your profile shows it.

> Until that first run finishes, the snake area is **blank — that's expected**, not a broken link. The default `GITHUB_TOKEN` already has the write permission the workflow needs; no extra secret required for the snake.

## Fill in your socials (30 seconds)

In `README.md`, find the commented `Connect` block, drop in your real X / LinkedIn / website URLs, and uncomment the lines you want. The **email badge is already wired**.

## Optional — `lowlighter/metrics` (rich SVG: language breakdown + isometric calendar)

1. Create a **classic** PAT with `public_repo` scope: <https://github.com/settings/tokens>.
2. Repo → Settings → Secrets and variables → Actions → **New repository secret** → name `METRICS_TOKEN`, value = the PAT.
3. Keep `.github/workflows/metrics.yml`, run it once from the Actions tab.
4. Add `<img src="./github-metrics.svg" width="100%" alt="metrics" />` wherever you want it in the README.
   Don't want it? Just delete `metrics.yml`.

## ⚠️ Reliability note — the stats card & trophies (read this)

Two widgets read your data through **GitHub's API server-side**, so they depend on a *shared public instance* that is frequently rate-limited by GitHub:

- `github-readme-stats.vercel.app` (stats + top-languages) → sometimes `503`
- `github-profile-trophy.vercel.app` (trophies) → sometimes `402`

On a live profile they usually render once the shared instance cools down, but for a **rock-solid, never-blank** profile, self-host the stats card (5 min, free, the move every top profile makes):

1. Go to <https://github.com/anuraghazra/github-readme-stats#deploy-on-your-own-vercel-instance> and click **Deploy** (imports the repo to your Vercel + needs a GitHub PAT — the wizard walks you through it).
2. You'll get your own URL, e.g. `https://your-app.vercel.app`.
3. In `README.md`, replace **both** `github-readme-stats.vercel.app` hosts with `your-app.vercel.app` (the stats card *and* the top-langs card). Same query params, now zero 503s.
4. Trophies: the shared instance is the only easy option; it recovers on its own, or you can self-host `ryo-ma/github-profile-trophy` the same way. If you'd rather not risk a blank block, delete the trophy `<img>` — everything else stays gorgeous.

> The pure-renderer widgets (capsule-render hero/footer, typing tagline, skillicons, streak, activity graph, profile views) don't touch the GitHub API and were verified **200 OK** — those never flake.

## Final check

Open <https://github.com/prodev2025> in **both** light and dark mode. Hero animates, tagline cycles, stats/streak/trophies load, snake plays, footer wave shows. Hard-refresh once if a stats image is cached blank (the free services warm up on first hit).

---

### What's on the profile (every widget is live + free + reads only public data — no fabricated numbers)

| Section | Widget |
|---|---|
| Hero + footer waves | capsule-render (`kyechan99/capsule-render`) |
| Typing tagline | readme-typing-svg (`DenverCoder1`) |
| Tech stack strip | skillicons.dev |
| Stats / top langs | github-readme-stats (`anuraghazra`) |
| Streak | streak-stats (`DenverCoder1`) |
| Trophies | github-profile-trophy (`ryo-ma`) |
| Snake contribution game | Platane/snk (GitHub Action) |
| Activity graph | github-readme-activity-graph (`Ashutosh00710`) |
| Profile views | komarev ghpvc |
| Metrics *(optional)* | lowlighter/metrics |

**Design system:** one cyan→violet→magenta gradient (`#00F5FF` / `#8B5CF6` / `#FF00E5`) on GitHub-dark, `tokyonight` theme across all stat cards with borders hidden for cohesion.
