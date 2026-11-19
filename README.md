WhatsApp AI Auto-Reply & Manager
(Versi Terbaru Lengkap)
Sistem auto-reply WhatsApp berbasis whatsapp-web.js, Google Gemini (
gemini-2.5-flash & gemini-2.5-flash-lite), SQLite ( wa_memory.db),
ExcelJS ( rekap_prospek.xlsx), Dashboard Web, dan Kontrol Jarak Jauh
Telegram.
Struktur File
index.js — Worker utama bot WhatsApp, AI memory, pencatat prospek
Excel, scheduler laporan harian, listener perintah Telegram ( /balas, /kirim,
/cari, /prospek, /status, /laporan, /jeda, /aktif), serta worker pengirim pesan
& lampiran dari dashboard.
dashboard.js — Server backend Express.js untuk mengelola memori
kontak, balas chat + unggah lampiran PDF/gambar, editor Knowledge
Base .md, rekap prospek Excel, dan pengaturan jam operasional.
public/index.html — Antarmuka web responsif (Tailwind CSS).
knowledge/ — Folder dokumen Knowledge Base Markdown ( .md / .txt).
exports/ — Lokasi penyimpanan otomatis rekap_prospek.xlsx.
uploads/outbound/ — Penyimpanan sementara lampiran PDF/gambar
yang dikirim dari Dashboard atau Telegram.
ecosystem.config.js — Konfigurasi PM2 untuk menjalankan wa-bot dan
wa-dashboard.
.env.example — Template variabel lingkungan (salin menjadi .env
sebelum menjalankan)


Cara Instalasi
1. Salin .env.example menjadi .env dan isi kredensial Anda:

Cara Instalasi
1. Salin .env.example menjadi .env dan isi kredensial Anda:
cp .env.example .env
'cp .env.example .env
```1. Pasang dependensi Node.js:
```bash
npm install
```1. Jalankan melalui PM2:
```bash
pm2 start ecosystem.config.js
```1. Cek log `wa-bot` (`pm2 logs wa-bot`) untuk memindai QR Code WhatsApp pertama kali, lalu
akses Dashboard Web di `http://localhost:3000`.'