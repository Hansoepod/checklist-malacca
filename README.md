# Papan Kepatuhan Laporan — Vercel Wrapper

Static wrapper yang meng-iframe web app Google Apps Script, supaya bisa diakses
lewat domain sendiri via Vercel.

## Setup

1. Deploy Google Apps Script sebagai Web App:
   - Execute as: **Me**
   - Who has access: **Anyone**
   - Salin Web App URL (format: `https://script.google.com/macros/s/XXXXX/exec`)

2. Buka `index.html`, cari baris:
   ```html
   src="https://script.google.com/macros/s/GANTI_DENGAN_DEPLOYMENT_ID_KAMU/exec"
   ```
   Ganti dengan Web App URL kamu.

3. Push ke GitHub, connect repo ini ke Vercel, deploy.

4. Tambahkan custom domain di Vercel dashboard (Project → Settings → Domains),
   ikuti instruksi update DNS (biasanya tambah CNAME atau A record di provider domain kamu).

## Update deployment GAS di kemudian hari

Setiap kali kamu bikin **New deployment** baru di Apps Script (bukan "Manage
deployments > edit versi lama"), URL-nya akan berubah — jangan lupa update
`index.html` juga. Kalau mau URL tetap sama selamanya, selalu update lewat
**Manage deployments → pensil edit → New version → Deploy** (bukan bikin
deployment baru dari nol).
