# Mianatra Malagasy — Malagasy Tutor

A single-file, offline-capable web app for learning beginner Malagasy:
lessons, flashcards, quizzes, listening, speaking practice, level tests,
and progress tracking (saved in the browser via localStorage).

`index.html` is the entire app — no build step, no dependencies.

## Run locally

Just open `index.html` in a browser (Chrome recommended for the best
speech-synthesis and microphone support).

## Deploy to GitHub + Vercel

### 1. Put it on GitHub

From this folder:

```bash
git init
git add index.html README.md
git commit -m "Initial commit: Mianatra Malagasy tutor"
# create an empty repo at github.com/new (e.g. "malagasy-tutor"), then:
git remote add origin https://github.com/<your-username>/malagasy-tutor.git
git branch -M main
git push -u origin main
```

### 2. Link it to Vercel

**Option A — Vercel dashboard (easiest):**
1. Go to vercel.com → **Add New… → Project**.
2. **Import** your `malagasy-tutor` GitHub repo.
3. Framework preset: **Other**. No build command, no output dir — it's static.
4. Click **Deploy**. Every future `git push` auto-deploys.

**Option B — Vercel CLI:**
```bash
npm i -g vercel
vercel        # first run links/creates the project
vercel --prod # production deploy
```

That's it — Vercel serves `index.html` at the root, so the app loads immediately.

## Notes / known limitations
- Vocabulary and phonetics were drafted and should be verified against an
  authoritative Malagasy source before relying on them for study.
- Audio uses the browser's built-in voices (no native Malagasy voice exists in
  most browsers), so pronunciation playback is approximate.
- Speaking practice uses a sound-similarity scorer, not a true Malagasy speech
  model — treat the score as a guide, not a grade.
