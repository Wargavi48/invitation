# Invitation — Halaman Undangan (GitHub Pages)

Halaman undangan statis untuk tamu, di-deploy sebagai **project site** GitHub Pages:

**URL:** `https://USERNAME-GITHUB.github.io/invitation/`

## Isi repo
- `index.html` — halaman undangan
- `config.js` — kredensial Supabase, URL undangan, & isi acara (satu-satunya file yang perlu diedit)
- `style.css` — styling
- `asset/` — gambar-gambar

> ⚠️ Sebelum deploy: buka `config.js` dan ganti `USERNAME-GITHUB` dengan username GitHub kamu.

## Deploy ke GitHub Pages
1. Buat repo baru di GitHub dengan nama **persis** `invitation` (public).
2. Dari folder ini, push ke repo tersebut:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/USERNAME-GITHUB/invitation.git
   git push -u origin main
   ```
3. Di GitHub: **Settings → Pages** → Source: **Deploy from a branch** → branch `main`, folder `/ (root)` → **Save**.
4. Tunggu 1–2 menit, lalu buka `https://USERNAME-GITHUB.github.io/invitation/`.

## Link personal tamu
Link yang dibuat admin berbentuk:
```
https://USERNAME-GITHUB.github.io/invitation/?to=slug-tamu
```
