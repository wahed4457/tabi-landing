# AGENTS.md

## Cursor Cloud specific instructions

Tabi is a **static** Arabic (RTL) marketing landing page — a single `index.html` plus `assets/`. There is **no build step, no package manager, no lockfile, and no lint/test tooling** in this repo.

### Run (development)
Serve the folder as static files, e.g.:
- `npx serve . -l 3000` (documented in `README.md`), or
- `python3 -m http.server 3000` (no install needed)

Then open `http://localhost:3000/`. All asset paths are relative (`assets/...`).

### Notes / gotchas
- CTA links are hardcoded constants near the bottom of `index.html` (`APK_URL`, `WEBAPP_URL`). `WEBAPP_URL` defaults to the placeholder `https://app.tabi.example.com`, which does **not** resolve — clicking the "open web app" CTA hitting a DNS error is expected until a real URL is set.
- This landing page does not call Supabase or any backend; it needs no environment variables or secrets to run.
- There is no lint/test/build command to run; validation is loading the page and confirming assets render.
