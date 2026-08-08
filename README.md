# Invitation — Halaman Undangan (GitHub Pages)

Halaman undangan statis untuk tamu, di-deploy sebagai **project site** GitHub Pages:

**URL:** `https://USERNAME-GITHUB.github.io/invitation/`

## Isi repo
- `index.html` — halaman undangan
- `config.js` — kredensial Supabase, URL undangan, & isi acara (satu-satunya file yang perlu diedit)
- `style.css` — styling
- `asset/` — gambar-gambar

> ⚠️ `config.js` adalah **template** — `SUPABASE_URL` & `SUPABASE_ANON_KEY` diisi otomatis dari repo secrets saat build.
> `GITHUB_USERNAME` & isi acara (`EVENT`) tetap diedit manual di `config.js`.

## Deploy ke GitHub Pages (via GitHub Actions)
1. Buat repo baru di GitHub dengan nama **persis** `invitation` (public).
2. Tambahkan repo secrets (wajib, lihat bagian "GitHub Repository Secrets").
3. Dari folder ini, push ke repo tersebut:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/USERNAME-GITHUB/invitation.git
   git push -u origin main
   ```
4. Di GitHub: **Settings → Pages** → Source: **GitHub Actions** (bukan "Deploy from a branch").
5. Workflow `.github/workflows/deploy.yml` otomatis build & deploy tiap push ke `main`.
6. Cek tab **Actions** di repo, lalu buka `https://USERNAME-GITHUB.github.io/invitation/`.

## Link personal tamu
Link yang dibuat admin berbentuk:
```
https://USERNAME-GITHUB.github.io/invitation/?to=slug-tamu
```

## GitHub Repository Secrets (wajib — dipakai workflow saat build)
1. Buka repo di GitHub → **Settings → Secrets and variables → Actions → New repository secret**.
2. Tambahkan **dua** secret di repo `invitation`:
   - `SUPABASE_URL` → `https://brahomjawmfckgtzgaea.supabase.co`
   - `SUPABASE_ANON_KEY` → key anon dari Supabase Dashboard
3. Workflow `.github/workflows/deploy.yml` membaca secret ini dan menyuntikkannya ke `config.js` saat build, lalu deploy ke Pages.

> `SUPABASE_ANON_KEY` **publik by design** — secret hanya menjauhkannya dari source repo, nilainya tetap tampil di JS situs.
