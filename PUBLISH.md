# 🚀 Publish your 100/10 aura profile — prodev2025

Your special profile README only shows on your profile if it lives in a **public repo named exactly `prodev2025`** (same as your username). Everything below is already prepared in `C:\Users\lasha\prodev2025`.

## What's in this build
| File | What it is |
|---|---|
| `README.md` | the profile |
| `assets/hero.svg` | **bespoke hand-authored animated hero** (glowing neon wordmark — nobody else has this) |
| `.github/workflows/snake.yml` | generates the 🐍 snake → `output` branch |
| `.github/workflows/profile-3d.yml` | generates the **3D isometric contribution skyline** |
| `.github/workflows/metrics.yml` | optional rich metrics (isocalendar, languages, habits, achievements) |

## 1 — Create + push

```bash
# Create a PUBLIC repo named exactly prodev2025 (no README) at https://github.com/new
cd ~/prodev2025
git remote add origin https://github.com/prodev2025/prodev2025.git
git push -u origin main
```
> Branch is already `main`. If the push hangs on auth, run it here: `! git -C ~/prodev2025 push -u origin main`

## 2 — Seed the animated visuals (one-time — they're blank until then)

Repo → **Settings → Actions → General → Workflow permissions** → set **Read and write permissions** → Save. Then **Actions** tab:

1. **GitHub-Profile-3D-Contrib** → Run workflow. Creates `./profile-3d-contrib/profile-night-rainbow.svg`.
2. **Generate Snake** → Run workflow. Creates the `output` branch with `github-snake.svg` / `github-snake-dark.svg`.

Until each runs once, that image area is **blank — expected, not broken**. Both use the built-in `GITHUB_TOKEN`; no PAT needed.

## 3 — ⭐ Make the stats cards bulletproof (do this — the shared host is flaky)

The **stats card, featured pin, and top-languages** all call `github-readme-stats.vercel.app`, a shared public instance that is **frequently rate-limited / down (503/429)**. As of right now it's returning 503. The fix every elite profile uses — **host your own** (5 min, free):

1. Open <https://github.com/anuraghazra/github-readme-stats#deploy-on-your-own-vercel-instance> → **Deploy** (imports to your Vercel, walks you through adding a GitHub PAT).
2. You get your own URL, e.g. `https://your-app.vercel.app`.
3. In `README.md`, replace **all three** `github-readme-stats.vercel.app` hostnames (stats, `/api/pin/`, `/api/top-langs/`) with `your-app.vercel.app`. Same params — now zero 503s, ever.

> Don't want to self-host? Leave it; the cards render whenever the shared instance recovers. But the hero, 3D skyline, snake, activity graph, and skillicons don't touch that host and are rock-solid.

## 4 — Featured pin slug

The pin points at `repo=turbogem-backend`. It renders only if a **public** repo with that exact name exists under `prodev2025`. Your local copy is `turbogem-backend-main` — if the published repo's name differs, update the `repo=` param in the `### Featured` block (or remove that block).

## 5 — Socials + optional metrics

- In `README.md`, find the commented `Connect` block, drop in your real X / LinkedIn / website URLs, uncomment. **Email is already wired.**
- Optional metrics: create a **classic** PAT (scopes `repo`, `read:org`, `read:user`) → repo Settings → Secrets → Actions → new secret `METRICS_TOKEN` → run the **Metrics** Action → embed any `metrics.plugin.*.svg` it produces.

## 6 — Final check

Open <https://github.com/prodev2025> in **light + dark**. Confirm: hero animates, stack/pin/numbers load, 3D skyline + snake play, activity line + footer wave show. If a card is cached blank, cache-bust the **raw origin** with a *random* token (`?cb=ab12`), not a predictable `?v=1` (CDN-cached).

---

### The widgets (all live, free, stat-honest — no fabricated numbers)
hero `assets/hero.svg` (authored) · skillicons.dev · github-readme-stats (stats / pin / top-langs — self-host recommended) · yoshi389111 3D skyline · Platane/snk snake · github-readme-activity-graph · capsule-render dividers + footer · lowlighter/metrics (optional).

**Design system:** one cyan `#00F5FF` → violet `#8B5CF6` → magenta `#FF00E5` gradient on GitHub-dark `#0D1117`, exact brand hex (not presets) across every widget for one coherent palette.
