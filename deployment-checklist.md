# Deployment Checklist

Gunakan checklist ini sebelum deploy ke environment selain local.

## 1) Configuration

- [ ] Semua environment variable terisi sesuai target environment
- [ ] `JWT__KEY` sudah diganti dari default development
- [ ] `ConnectionStrings` menunjuk database target yang benar
- [ ] `REACT_APP_API_URL` sesuai URL backend environment

## 2) Security

- [ ] Secret tidak disimpan hardcoded di source code
- [ ] Gunakan secret manager/CI variables untuk credential
- [ ] Password database sudah memenuhi policy
- [ ] HTTPS/TLS aktif pada environment deployment

## 3) Application Validation

- [ ] Backend build sukses
- [ ] Frontend build sukses
- [ ] Mobile analyze/test sukses (jika termasuk release)
- [ ] Health check endpoint backend merespons normal

## 4) Data & Migration

- [ ] Backup database sudah dilakukan
- [ ] Migration sudah dieksekusi dan tervalidasi
- [ ] Seeder hanya dijalankan jika memang diperlukan

## 5) Smoke Test Pasca Deploy

- [ ] Login berhasil
- [ ] Endpoint terproteksi role berjalan sesuai policy
- [ ] Alur booking utama bisa dilakukan end-to-end
- [ ] Log aplikasi tidak menunjukkan error kritikal

## 6) Rollback Plan

- [ ] Strategi rollback disiapkan dan terdokumentasi
- [ ] Tim tahu langkah rollback jika deploy gagal
