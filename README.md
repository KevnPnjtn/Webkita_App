# WebKita

WebKita merupakan marketplace layanan digital berbasis web yang dirancang untuk menghubungkan pemilik bisnis dengan developer profesional dalam proyek pengembangan website. Platform ini bertujuan untuk memudahkan bisnis dalam menemukan layanan pengembangan yang sesuai, sekaligus menyediakan platform terpercaya bagi developer dan freelancer untuk menawarkan keahlian mereka.

Aplikasi ini menggunakan **arsitektur decoupled**, yaitu memisahkan frontend dan backend menjadi aplikasi yang independen dan saling terhubung melalui **REST API**.

---

## Deskripsi

WebKita dikembangkan untuk mengatasi tantangan yang dihadapi bisnis dalam mencari layanan pengembangan website yang terpercaya serta developer yang mencari peluang untuk menawarkan layanan mereka.

Platform ini dirancang menggunakan alur kerja berbasis proyek yang mendukung:

* Pemilik bisnis yang mencari layanan pengembangan website
* Developer dan freelancer yang menawarkan keahlian mereka
* Pencocokan layanan dan developer
* Manajemen proyek
* Proses transaksi yang aman
* Informasi proyek yang terpusat

---

## Fitur Utama

### Untuk Pemilik Bisnis

* Melihat layanan digital yang tersedia
* Menemukan developer atau layanan yang sesuai
* Mengajukan proyek pengembangan website
* Mengelola informasi proyek
* Mengunggah kebutuhan proyek dan dokumen pendukung
* Memantau perkembangan proyek

### Untuk Developer

* Menawarkan layanan pengembangan profesional
* Menerima dan mengelola peluang proyek
* Mengelola informasi terkait proyek
* Berkolaborasi dengan klien selama proses pengerjaan proyek

### Platform

* Pencocokan developer dan klien
* Manajemen proyek
* Alur transaksi yang aman
* Autentikasi dan otorisasi
* Komunikasi berbasis REST API antara frontend dan backend

---

## Arsitektur

WebKita menggunakan **arsitektur decoupled / REST API**, yang memungkinkan frontend dan backend dikembangkan, di-deploy, dan dipelihara secara independen.

```text
┌─────────────────────┐
│      Frontend       │
│  React + Vite       │
│  Tailwind CSS       │
└──────────┬──────────┘
           │
           │ REST API
           ▼
┌─────────────────────┐
│       Backend       │
│       Hono          │
│ Cloudflare Workers  │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│      Supabase       │
│ PostgreSQL + Auth   │
└─────────────────────┘
```

### Struktur Proyek

```text
WEBKITA-APPLICATION/

├── backend/
│   ├── src/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── middleware/
│   │   └── lib/
│   ├── .dev.vars
│   └── wrangler.jsonc
│
├── frontend/
│   └── src/
│
├── docker-compose.yml
└── README.md
```

---

## Teknologi yang Digunakan

| Lapisan        | Teknologi                          |
| -------------- | ---------------------------------- |
| Frontend       | React, Vite, Tailwind CSS          |
| Backend        | Hono, Cloudflare Workers, Wrangler |
| Database       | Supabase PostgreSQL                |
| Autentikasi    | JWT                                |
| Containerisasi | Docker, Docker Compose             |
| API            | REST API                           |

---

## Prasyarat

Sebelum menjalankan proyek, pastikan perangkat telah memiliki:

* **Node.js v22 atau lebih baru**
* **Docker & Docker Compose** *(opsional)*
* **Akun Supabase**
* **Wrangler CLI**

---

## Instalasi & Konfigurasi

### 1. Clone Repository

```bash
git clone https://github.com/KevnPnjtn/Webkita_App.git
cd Webkita_App
```

### 2. Konfigurasi Backend

Masuk ke direktori backend:

```bash
cd backend
```

Instal dependensi:

```bash
npm install
```

Jalankan server pengembangan Cloudflare Workers:

```bash
npx wrangler dev
```

Backend dapat diakses melalui:

```text
http://localhost:8787
```

### 3. Konfigurasi Frontend

Buka terminal baru dan masuk ke direktori frontend:

```bash
cd frontend
```

Instal dependensi:

```bash
npm install
```

Jalankan server pengembangan:

```bash
npm run dev
```

Frontend dapat diakses melalui:

```text
http://localhost:5173
```

---

## Konfigurasi Environment

Backend membutuhkan environment variables untuk menjalankan aplikasi dalam lingkungan pengembangan lokal.

Buat file berikut:

```text
backend/.dev.vars
```

File ini sengaja tidak disertakan dalam Git melalui `.gitignore`.

Konfigurasikan kredensial yang diperlukan:

```text
SUPABASE_URL=your_supabase_url

SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key

JWT_SECRET=your_jwt_secret
```

> **Penting:** Jangan pernah mengunggah `.dev.vars`, Supabase service-role key, JWT secret, atau kredensial sensitif lainnya ke repository.

---

## Menjalankan dengan Docker

Untuk menjalankan aplikasi menggunakan Docker Compose, gunakan perintah:

```bash
docker-compose up --build
```

Setelah proses selesai, layanan dapat diakses melalui:

| Layanan  | URL                   |
| -------- | --------------------- |
| Backend  | http://localhost:8787 |
| Frontend | http://localhost:5173 |

---

## Deployment

### Backend — Cloudflare Workers

Masuk ke direktori backend:

```bash
cd backend
```

Deploy backend menggunakan Wrangler:

```bash
npx wrangler deploy
```

Backend kemudian akan dijalankan pada lingkungan **Cloudflare Workers**.

---

## Struktur Repository

Proyek ini terdiri dari aplikasi frontend dan backend yang terpisah:

* **`backend/`** — REST API yang dibangun menggunakan Hono dan di-deploy ke Cloudflare Workers.
* **`frontend/`** — Single Page Application (SPA) yang dibangun menggunakan React, Vite, dan Tailwind CSS.
* **`docker-compose.yml`** — Konfigurasi Docker Compose untuk menjalankan layanan proyek.
* **`README.md`** — Dokumentasi proyek.

---

## Kontributor

| Nama | Kontak |
| ---- | ------ |
| Kevin Reynaldi Panjaitan | [kevinpanjaitan09@gmail.com](mailto:kevinpanjaitan09@gmail.com) |
| Rikardo Anju Sinaga | [anjo24696@gmail.com](mailto:anjo24696@gmail.com) |
| Yulia Nabila | [nabilayulia31@gmail.com](mailto:nabilayulia31@gmail.com) |

---
