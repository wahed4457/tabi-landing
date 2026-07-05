# Tabi Marketing Landing Page

Static Arabic marketing site for **Tabi** (Spenx Platforms). No build step — single `index.html` plus assets.

## Purpose

Promotes the Tabi app: download APK and open the web app. The landing page does **not** call Supabase directly. The Tabi product (Expo web / mobile) uses the Supabase project **tabi** (`https://hrpfkofstixwwxaojhdn.supabase.co`). CTAs on this page should point to that app via `WEBAPP_URL`.

## Edit download / app links

In `index.html`, find the script block near the bottom and change:

- `APK_URL` — direct link to your `.apk` (e.g. GitHub Releases asset)
- `WEBAPP_URL` — production URL of the Tabi Expo web app (not set in the main TABI repo yet; default is a placeholder)

Also update `<meta property="og:url">` to your live landing URL after deploy.

## Local preview

Open `index.html` in a browser, or:

```bash
npx serve .
```

All asset paths are relative (`assets/...`).

## Deploy on Vercel

1. Import this repository in [Vercel](https://vercel.com) (or run `npx vercel --prod` from this folder).
2. Framework preset: **Other** / static. Root directory: `.` (default).
3. No environment variables required for the current static setup.
4. After deploy, set `og:url` in `index.html` to your Vercel production domain and redeploy if needed.

## Repository layout

```
index.html      # Page + APK_URL / WEBAPP_URL constants
assets/         # mascot.png, app-icon.png, wordmark.svg
vercel.json     # Static hosting hints
.env.example    # Documented URL placeholders (not used at runtime)
```

## Security

Do not commit Supabase service role keys or backend secrets. This repo should only contain public marketing assets and public URLs.

