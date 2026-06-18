# Changes — ear training for jazz progressions

A browser-based ear-training prototype. It reads out a tune's key, tempo, feel and
form, then plays the changes (electric-piano comping, upright-style bass, a lead
voice, and swung ride) while speaking each chord — by **name** ("D minor seven") or
by **function** ("two minor / ii") — in time with the music.

No build step, no dependencies. Everything is in a single `index.html`.

## Run it locally

Just open `index.html` in a browser. Or serve it (so audio behaves consistently):

```bash
# Python
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Features

- Pre-roll intro: title, key, tempo, feel, form (spoken + on screen)
- Synced readout: chord names / functions / both
- Original guide-tone melody generated from each bar's chord tones
- Swing feel, adjustable tempo (60–220 bpm)
- Voice picker (uses the most natural voice your device offers)

> The audio is fully synthesized. The melody is an original line written to fit the
> changes — it is **not** a recording or the copyrighted tune.

---

## Putting this under version control with GitHub

You already created a GitHub account — here's the full first-time flow.

### 0. One-time setup (only once per machine)

```bash
git config --global user.name  "Your Name"
git config --global user.email "you@example.com"
```

### 1. Create an empty repo on GitHub

On github.com: **New repository** → name it e.g. `jazz-ear-trainer` →
**do not** add a README/license (you already have files) → Create.

### 2. Turn this folder into a repo and push

From the folder that contains `index.html` and `README.md`:

```bash
git init
git add .
git commit -m "Initial commit: jazz ear-training prototype"
git branch -M main
git remote add origin https://github.com/<your-username>/jazz-ear-trainer.git
git push -u origin main
```

### 3. The everyday loop (this is the practice you want)

```bash
git status                 # what changed?
git add index.html         # stage a specific file (or: git add .)
git commit -m "Add swing feel to the ride pattern"
git push                   # send commits to GitHub
```

Write one commit per meaningful change with a clear message. Reading your own
history later is the payoff.

### 4. Useful next commands to practice

```bash
git log --oneline          # see your history compactly
git diff                   # see unstaged changes before adding
git checkout -b feature-x  # make a branch to try something risky
git switch main            # go back to the main branch
git merge feature-x        # bring the branch's work into main
```

### 5. (Bonus) Host it live for free with GitHub Pages

Because the whole app is one `index.html`, GitHub can serve it as a website:

1. Repo → **Settings** → **Pages**
2. **Source**: Deploy from a branch → Branch: `main` → Folder: `/ (root)` → Save
3. Wait ~1 minute, then open `https://<your-username>.github.io/jazz-ear-trainer/`

Every `git push` to `main` updates the live site.

## .gitignore

A starter `.gitignore` is included so OS junk files don't get committed.
