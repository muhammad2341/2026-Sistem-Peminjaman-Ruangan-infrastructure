# 2026 Sistem Peminjaman Ruangan - Infrastructure

Folder ini berisi panduan dan template infrastruktur untuk local development dan persiapan deployment.

## Cakupan

- Orkestrasi lokal dengan Docker Compose
- Konfigurasi environment variable
- Checklist verifikasi sebelum deploy

## Menjalankan Stack Lokal

Jalankan dari root workspace:

```powershell
docker compose up --build
```

Stop stack:

```powershell
docker compose down
```

Hapus volume database (opsional):

```powershell
docker compose down -v
```

## Service yang Tersedia

- `db` - SQL Server 2022
- `backend` - ASP.NET Core API
- `frontend` - React app via Nginx

## Konfigurasi Penting

- Connection string backend mengarah ke host `db` dalam network compose.
- JWT key default hanya untuk development; wajib diganti untuk environment real.
- `REACT_APP_API_URL` harus menunjuk ke URL backend yang sesuai environment.

## File Pendukung di Folder Ini

- `.env.example` - template environment variable
- `deployment-checklist.md` - checklist readiness deploy

## Catatan Keamanan

- Jangan commit secret production ke repository.
- Gunakan secret manager untuk staging/production.
- Putar ulang (`rotate`) credential secara berkala.
