# Tugas Mandiri 2 — Responsive Page Layout

## 1. Tujuan

Membuat halaman profil mahasiswa yang responsif menggunakan
Tailwind CSS agar tampilan menyesuaikan ukuran layar.

## 2. Implementasi

Halaman menampilkan nama Softianto, NIM 2024520009,
foto profil, program studi, universitas, deskripsi,
tautan GitHub, dan informasi keahlian.

Tailwind CSS digunakan untuk mengatur tata letak,
warna, ukuran teks, jarak, dan responsivitas halaman.

## 3. Penerapan Responsive Layout

- `grid-cols-1`: menyusun konten menjadi satu kolom.
- `sm:grid-cols-[180px_1fr]`: menyusun foto dan informasi
  profil berdampingan pada breakpoint sm dan ukuran lebih besar.
- `px-4 sm:px-6`: menyesuaikan padding horizontal.
- `text-2xl sm:text-3xl`: menyesuaikan ukuran judul.
- `flex-wrap`: memungkinkan elemen keahlian berpindah baris
  jika ruang yang tersedia tidak mencukupi.

## 4. Hasil Pengujian

### A. Layar Laptop


Screenshot: `screenshot/tm2-layout-laptop.png`

### B. Layar 360 Piksel

Screenshot: `screenshot/tm2-layout-360px.png`

## 5. Kesimpulan

Halaman menggunakan utility Tailwind CSS untuk mengatur
tata letak yang menyesuaikan ukuran layar. Pengujian dilakukan
pada layar laptop dan lebar 360 piksel untuk memeriksa
keterbacaan teks, susunan elemen, dan tampilan halaman.