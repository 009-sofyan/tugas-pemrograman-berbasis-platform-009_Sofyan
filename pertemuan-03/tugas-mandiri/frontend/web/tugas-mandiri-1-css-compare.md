# Tugas Mandiri 1 — Perbandingan Component-Based CSS dan Utility-First

## 1. Tujuan

Tugas ini bertujuan untuk membandingkan pendekatan Component-Based CSS dengan Utility-First menggunakan Tailwind CSS dalam membuat kartu profil mahasiswa.

## 2. Implementasi

Saya membuat dua halaman kartu profil mahasiswa dengan konten yang sama, yaitu nama Softianto, NIM 2024520009, foto profil, dan tombol untuk melihat profil GitHub.

* **Component-Based CSS:** Menggunakan class CSS seperti `.card`, `.profile-photo`, `.profile-name`, dan `.btn`. Pengaturan tampilan ditulis dalam tag `<style>`.
* **Utility-First:** Menggunakan class utility Tailwind CSS secara langsung pada atribut `class` elemen HTML, seperti `flex`, `rounded-2xl`, `p-6`, dan `text-center`.

## 3. Hasil Pengujian

Kedua halaman diuji pada ukuran layar laptop dan layar dengan lebar 360 piksel. Pengujian dilakukan untuk melihat kesesuaian tampilan kartu, keterbacaan teks, posisi tombol, dan responsivitas halaman.

| Aspek                  | Component-Based CSS                              | Utility-First                                  |
| ---------------------- | ------------------------------------------------ | ---------------------------------------------- |
| Penulisan styling      | Menggunakan class CSS yang didefinisikan sendiri | Menggunakan class utility Tailwind CSS         |
| Pengelolaan CSS        | Aturan styling terpusat dalam tag `<style>`      | Styling ditulis langsung pada class HTML       |
| Kemudahan membaca HTML | HTML relatif lebih ringkas                       | HTML memiliki banyak class utility             |
| Perubahan desain       | Dapat dilakukan melalui aturan CSS               | Dapat dilakukan dengan mengganti class utility |
| Responsivitas          | Diatur menggunakan CSS                           | Dapat menggunakan breakpoint Tailwind          |

## 4. Hasil Pengamatan

Berdasarkan implementasi, Component-Based CSS membuat struktur HTML lebih ringkas karena aturan tampilannya dikelompokkan dalam class CSS tersendiri. Sementara itu, Utility-First memudahkan pengaturan tampilan langsung pada elemen HTML tanpa harus membuat banyak aturan CSS sendiri.

Menurut saya, Component-Based CSS lebih mudah dipahami ketika baru belajar dasar CSS karena struktur HTML dan styling terpisah. Namun, Tailwind CSS juga praktis untuk membuat dan mengubah desain dengan cepat setelah memahami class utility yang tersedia.

## 5. Dokumentasi Pengujian

Dokumentasi screenshot yang dilampirkan:

1. Tampilan Component-Based CSS pada layar laptop.
2. Tampilan Component-Based CSS pada layar 360 piksel.
3. Tampilan Utility-First pada layar laptop.
4. Tampilan Utility-First pada layar 360 piksel.

## 6. Kesimpulan

Kedua pendekatan dapat digunakan untuk membuat kartu profil dengan konten dan tampilan yang serupa. Component-Based CSS mengutamakan pengelompokan aturan styling dalam class CSS, sedangkan Utility-First mengutamakan penggunaan class utility langsung pada elemen HTML. Pilihan pendekatan dapat disesuaikan dengan kebutuhan dan kenyamanan pengembang.
