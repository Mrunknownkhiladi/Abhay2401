# Setup Guide: GitHub Profile README (AbhayRaj2401)

## Files in this package
```text
AbhayRaj2401/
├── README.md                          <- the profile README
├── make_profile_card.py               <- embeds your photo into the animated ring (optional helper)
├── SETUP_GUIDE.md                     <- this guide (do not upload)
├── assets/
│   ├── profile-card.svg               <- animated neon ring + photo
│   └── engineering-equation.svg       <- animated "Engineering + Code" visual
└── .github/workflows/snake.yml        <- contribution snake workflow
```
Upload everything except `SETUP_GUIDE.md` (and `make_profile_card.py` if you prefer; it is harmless).

## 1. Create the profile repository
1. Go to https://github.com/new
2. Repository name: **`AbhayRaj2401`** (must exactly match your username)
3. Set it to **Public**
4. Tick **Add a README file** (you will overwrite it)
5. Click **Create repository**. GitHub shows "You found a secret repo" once the name matches.

## 2. Where to put README.md
Put `README.md` in the **root** of that repository. Edit the existing one on GitHub (pencil icon), paste the full content, and commit to `main`.
Upload `assets/` the same way: **Add file -> Upload files**, drag the `assets` folder, commit.

## 3. Add your profile photo
**Option A (animated ring, recommended)**
1. Clone the repo, or put `make_profile_card.py` next to the `assets` folder.
2. Run: `pip install pillow` (optional, auto-crops to a square), then `python make_profile_card.py my-photo.jpg`
3. This writes your photo into `assets/profile-card.svg`. Commit and push it.

**Option B (quick, no animation)**
In `README.md`, delete the Option A `<img>` line, un-comment the Option B line, and replace `YOUR_PROFILE_IMAGE_URL` with a public URL of your photo (for example a GitHub avatar: `https://github.com/AbhayRaj2401.png`). It is circle-cropped automatically.

## 4. Create the GitHub Actions workflow
1. In the repo click **Add file -> Create new file**
2. In the name box type exactly: `.github/workflows/snake.yml` (typing the `/` creates the folders)
3. Paste the contents of `snake.yml`
4. Click **Commit changes** to `main`

## 5. Enable and run the contribution snake
1. Repo **Settings -> Actions -> General -> Workflow permissions -> Read and write permissions -> Save**
2. Open the **Actions** tab, choose **Generate Contribution Snake**, click **Run workflow -> Run workflow**
3. Wait about a minute for the green check.
4. How it works: the `Platane/snk` action reads your contribution calendar and builds animated SVGs. The second step pushes them to a branch named **`output`**. The workflow then re-runs every 12 hours and on every push to `main`.
5. The README already displays it through these URLs:
```text
https://raw.githubusercontent.com/AbhayRaj2401/AbhayRaj2401/output/github-contribution-grid-snake-neon.svg
https://raw.githubusercontent.com/AbhayRaj2401/AbhayRaj2401/output/github-contribution-grid-snake.svg   (light mode)
```
If the snake shows as broken, the workflow has not completed yet. Check the Actions tab for errors.

## 6. Replace all placeholders
Use your editor's find (Ctrl+F) in `README.md`:

| Placeholder | Replace with |
| :-- | :-- |
| `YOUR_PROFILE_IMAGE_URL` | Photo URL (Option B only) |
| `YOUR_LINKEDIN_URL` | Your LinkedIn profile link |
| `YOUR_YOUTUBE_URL` | Your YouTube channel link |
| `YOUR_EMAIL` | Your email address (inside `mailto:`) |
| `YOUR_APNAMANDI_REPOSITORY_URL` | ApnaMandi GitHub repo link |
| `YOUR_APNAMANDI_LIVE_URL` | ApnaMandi deployed site link |
| `YOUR_RADAR_REPOSITORY_URL` | IoT Radar repo link |
| `YOUR_AI_IOT_ROBOT_REPOSITORY_URL` | AI + IoT Robot repo link |

If you do not have a link yet (for example YouTube), delete that whole `<a>...</a>` line so no dead button shows.

## 7. Add more projects
Copy one project `<tr>...</tr>` block inside the Featured Projects `<table>` and edit the title, description, technology, and link buttons. Keep the blank lines inside `<td>` so Markdown headings still render.

## 8. Add social links
Copy any badge line in **Connect With Me** and change the URL, the badge label, and the `logo=` name (any slug from https://simpleicons.org).

## 9. Fill achievements
Edit the table rows in **Achievements & Certifications**, for example: `| ☕ Java Certifications | Oracle Java SE, 2026 |`.

## 10. Customize the theme
Accent colors used throughout: cyan `00F5FF`, blue `3B82F6`, purple `A371F7`, background `0D1117`.
- Header and footer: edit the `color=0:...,50:...,100:...` gradient in the capsule-render URLs.
- Stats cards: change `title_color`, `icon_color`, `ring_color`, `bg_color`.
- Typing text: change `color=`, `font=`, `lines=` (use `+` for spaces, `%26` for `&`).
- Snake colors: change `color_snake` and `color_dots` in `snake.yml`.
- Equation animation: edit `assets/engineering-equation.svg` (text and `dur` timing).

## Notes on reliability
- The stats, streak, and activity-graph cards use free public servers and are occasionally slow or rate-limited. If one goes blank, wait and refresh; it normally recovers.
- Stats include private contributions only if enabled under your profile's **Contribution settings -> Private contributions**.
- GitHub caches images, so changes can take a few minutes to appear.
