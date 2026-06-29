# 🚀 Publish your profile — KernelLord (Lasha Dev)

Your profile README only shows on your profile if it lives in a **public repo named exactly `KernelLord`** (same as your username). Everything is prepared in the local folder `C:\Users\lasha\prodev2025` (folder name is cosmetic — the published repo is `KernelLord/KernelLord`).

## What's in this build
| File | What it is |
|---|---|
| `README.md` | the profile — gold + purple, confident-for-stealth |
| `assets/banner.svg` | **bespoke blinking-eyes banner** (your eyes art + gold `KernelLord` wordmark, lids blink every ~5s) |
| `.github/workflows/snake.yml` | 🐍 snake → `output` branch |
| `.github/workflows/profile-3d.yml` | 3D isometric contribution skyline |
| `.github/workflows/metrics.yml` | optional rich metrics (PAT) |

## 1 — Create + push
```bash
# Create a PUBLIC repo named exactly KernelLord (no README) at https://github.com/new
cd ~/prodev2025
git remote add origin https://github.com/KernelLord/KernelLord.git
git push -u origin main
```
> Branch is `main`. If the push hangs on auth, run it here: `! git -C ~/prodev2025 push -u origin main`

## 2 — Set the Madara profile picture (manual — avatars can't be set from a repo)
GitHub → top-right avatar → **Settings → Profile → Profile picture → Edit → Upload a photo** → choose `C:\Users\lasha\Desktop\d42bbae6-6fcc-470f-b089-28eedf3d5ecb.jpg` (the Madara one). Save. That sets the round avatar; the **eyes** image is your README banner.

## 3 — ⭐ Light up the contribution graphs (important for a private-repo account)
Your work is private, so by default the graphs look empty. Fix it:
**Settings → Profile → Contributions & activity →** enable **“Include private contributions on my profile.”**
Now the activity graph, 3D skyline, and snake reflect your *private* TurboGem commits (as counts, no code exposed).

## 4 — Seed the animated visuals (one-time — blank until then)
Repo → **Settings → Actions → General → Workflow permissions** → **Read and write** → Save. Then **Actions** tab:
1. **GitHub-Profile-3D-Contrib** → Run workflow → creates `./profile-3d-contrib/profile-night-rainbow.svg`.
2. **Generate Snake** → Run workflow → creates the `output` branch (`github-snake.svg` / `github-snake-dark.svg`).

Until each runs once that image is **blank — expected, not broken.** Both use the built-in `GITHUB_TOKEN`.

## 5 — ⭐ Make the stats card bulletproof + show private numbers
The `### systems log` stats card uses `github-readme-stats.vercel.app`, a shared host that is **often rate-limited (503)** — and on the shared host `count_private` **can't see your private commits**. Self-hosting fixes both (5 min, free):
1. <https://github.com/anuraghazra/github-readme-stats#deploy-on-your-own-vercel-instance> → **Deploy** (imports to your Vercel; add a GitHub PAT when prompted — that PAT is what unlocks private counts).
2. In `README.md`, replace the `github-readme-stats.vercel.app` hostname with your `your-app.vercel.app`. Now it's always up **and** your private TurboGem work shows as real numbers.
> The streak card (different host) and everything else already verified working.

## 6 — Socials + optional metrics
- In `README.md`, find the commented `X` / `LinkedIn` block, add your real URLs, uncomment. Email is already wired.
- Optional metrics: classic PAT (`repo`, `read:org`, `read:user`) → repo secret `METRICS_TOKEN` → run the **Metrics** Action → embed any `metrics.plugin.*.svg`.

## 7 — Final check
Open <https://github.com/KernelLord> in **light + dark**. Confirm: the **eyes blink**, the gold wordmark + typing line + badge row show, the neofetch boot-log renders, skillicons load, activity/skyline/snake show (after Step 3+4), footer wave plays. Hard-refresh once if a card is cached blank.

---

### Widgets (all live, free, stat-honest — no fabricated numbers)
`assets/banner.svg` (authored blinking eyes) · readme-typing-svg (gold manifesto) · shields.io status badges · skillicons.dev · github-readme-activity-graph · yoshi389111 3D skyline · Platane/snk snake · github-readme-stats + streak-stats (self-host stats recommended) · capsule-render dividers + footer.

**Design system:** one gold `#F5B301`/`#FFC83D` + purple `#A855F7`/`#8B5CF6` + crimson `#B11226` palette on near-black `#0D0D0D`, exact hex on every widget (no stock themes) — cohesive with your eyes art.
