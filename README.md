# 📝 Aplikasi Catatan dengan Flutter & Serverpod (Docker)

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)
![Serverpod](https://img.shields.io/badge/Serverpod-0175C2?style=for-the-badge&logo=dart&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

Aplikasi lengkap untuk membuat catatan dengan Flutter di frontend dan Serverpod di backend, siap dijalankan dengan Docker.

## 🌟 Fitur Utama

- **Aplikasi Flutter full-stack** dengan backend Serverpod
- **Sudah ter-dockerisasi** untuk kemudahan deployment
- **Dukungan multi-platform** (Android, iOS, Web, Desktop)
- **Workflow CI/CD** untuk AWS dan GCP
- **Arsitektur modern** dengan pemisahan layer yang jelas

## 🏗 Struktur Proyek

```plaintext
note-serverpod-docker/
├── github/workflows/          # Pipeline CI/CD
│   ├── deployment-aws.yml
│   └── deployment-gcp.yml
│
├── notes_client/             # Kode client yang dipakai bersama
│   ├── lib/                  # Model dan utilitas client
│   ├── src/protocol/         # Definisi protocol yang dipakai bersama
│   └── pubspec.yaml
│
├── notes_flutter/            # Frontend Flutter
│   ├── lib/                  # Kode aplikasi Flutter
│   ├── android/              # Kode spesifik Android
│   ├── ios/                  # Kode spesifik iOS
│   └── pubspec.yaml
│
├── notes_server/             # Backend Serverpod
│   ├── lib/                  # Logika bisnis server
│   ├── migrations/           # Migrasi database
│   ├── config/               # File konfigurasi
│   ├── Dockerfile            # Konfigurasi Docker
│   └── docker-compose.yaml   # Setup docker compose
│
└── README.md                 # Dokumentasi proyek
```

## 🚀 Memulai

### Prasyarat
- Flutter SDK
- Dart SDK
- Docker
- Serverpod CLI

### Instalasi
1. Clone repositori:
   ```bash
   git clone https://github.com/teukualdieaulia/note-serverpod-docker.git
   cd note-serverpod-docker
   ```

2. Jalankan container Docker:
   ```bash
   cd notes_server
   docker-compose up -d
   ```

3. Jalankan aplikasi Flutter:
   ```bash
   cd ../notes_flutter
   flutter pub get
   flutter run
   ```

## 🔧 Deployment

Proyek ini sudah menyediakan workflow CI/CD untuk:

### Deployment ke AWS
```yaml
# .github/workflows/deployment-aws.yml
name: Deploy ke AWS

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: cd notes_server && docker-compose up -d --build
```

### Deployment ke GCP
```yaml
# .github/workflows/deployment-gcp.yml
name: Deploy ke GCP

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: cd notes_server && gcloud app deploy
```

## 📚 Dokumentasi

- [Dokumentasi Serverpod](https://serverpod.dev)
- [Dokumentasi Flutter](https://flutter.dev/docs)
- [Dokumentasi Docker](https://docs.docker.com)

## 🤝 Berkontribusi

Kontribusi sangat diterima! Ikuti langkah berikut:
1. Fork proyek ini
2. Buat branch fitur baru (`git checkout -b fitur/FiturKeren`)
3. Commit perubahan Anda (`git commit -m 'Menambahkan FiturKeren'`)
4. Push ke branch (`git push origin fitur/FiturKeren`)
5. Buat Pull Request

## 📜 Lisensi

Dilisensikan di bawah MIT License. Lihat `LICENSE` untuk informasi lebih lanjut.

---

<div align="center">
  <sub>Dibuat dengan ❤ oleh <a href="https://github.com/teukualdieaulia">aldi tampan</a></sub>
</div>
