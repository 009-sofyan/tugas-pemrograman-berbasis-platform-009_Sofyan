# Tugas Mandiri 3 — Authentication dan Authorization

**Nama:** Softianto
**NIM:** 2024520009
**Program Studi:** Informatika

## 1. Pengertian Authentication dan Authorization

**Authentication** adalah proses memeriksa identitas pengguna untuk memastikan bahwa pengguna benar-benar orang yang mengaku sebagai dirinya. Contohnya, pengguna memasukkan username dan password untuk login.

**Authorization** adalah proses menentukan apakah pengguna yang sudah teridentifikasi memiliki izin untuk mengakses fitur atau melakukan tindakan tertentu. Contohnya, mahasiswa hanya dapat melihat datanya sendiri, sedangkan administrator dapat mengelola data pengguna.

## 2. Perbedaan Authentication dan Authorization

| Aspek            | Authentication                      | Authorization                                |
| ---------------- | ----------------------------------- | -------------------------------------------- |
| Tujuan           | Memastikan identitas pengguna       | Memastikan hak akses pengguna                |
| Pertanyaan utama | Siapa pengguna ini?                 | Apa yang boleh dilakukan pengguna ini?       |
| Proses           | Login dan verifikasi identitas      | Pemeriksaan role dan permission              |
| Contoh           | Memasukkan username dan password    | Memeriksa izin menghapus data                |
| Waktu penerapan  | Ketika identitas perlu diverifikasi | Ketika pengguna meminta akses ke sumber daya |

## 3. Matriks Role dan Hak Akses

Berikut contoh matriks hak akses untuk aplikasi pengelolaan data mahasiswa.

| Fitur                          | Tamu  | Mahasiswa | Admin |
| ------------------------------ | ----- | --------- | ----- |
| Melihat informasi publik       | Ya    | Ya        | Ya    |
| Melihat data profil sendiri    | Tidak | Ya        | Ya    |
| Mengubah profil sendiri        | Tidak | Ya        | Ya    |
| Melihat seluruh data mahasiswa | Tidak | Tidak     | Ya    |
| Menambahkan data mahasiswa     | Tidak | Tidak     | Ya    |
| Mengubah data mahasiswa lain   | Tidak | Tidak     | Ya    |
| Menghapus data mahasiswa       | Tidak | Tidak     | Ya    |

Keterangan:

* **Tamu:** pengguna yang belum login.
* **Mahasiswa:** pengguna yang sudah login dengan role mahasiswa.
* **Admin:** pengguna yang sudah login dengan hak akses administrator.

## 4. Contoh Matriks Endpoint

Endpoint berikut merupakan contoh rancangan API untuk menggambarkan hubungan antara role dan hak akses.

| Method | Endpoint             | Tamu      | Mahasiswa                      | Admin     |
| ------ | -------------------- | --------- | ------------------------------ | --------- |
| GET    | `/api/public`        | Diizinkan | Diizinkan                      | Diizinkan |
| GET    | `/api/profil`        | Ditolak   | Diizinkan                      | Diizinkan |
| PATCH  | `/api/profil`        | Ditolak   | Diizinkan untuk profil sendiri | Diizinkan |
| GET    | `/api/mahasiswa`     | Ditolak   | Ditolak                        | Diizinkan |
| POST   | `/api/mahasiswa`     | Ditolak   | Ditolak                        | Diizinkan |
| DELETE | `/api/mahasiswa/:id` | Ditolak   | Ditolak                        | Diizinkan |

Hak akses pada implementasi sebenarnya harus diterapkan dan diperiksa oleh backend, bukan hanya dengan menyembunyikan tombol pada frontend.

## 5. Perbedaan HTTP 401 dan HTTP 403

**HTTP 401 Unauthorized**

Status ini menunjukkan bahwa permintaan belum memiliki autentikasi yang valid. Misalnya, pengguna mengakses endpoint yang memerlukan login tanpa mengirim token atau menggunakan token yang tidak valid.

**HTTP 403 Forbidden**

Status ini menunjukkan bahwa server menolak akses karena pengguna tidak memiliki izin yang diperlukan. Misalnya, mahasiswa sudah login tetapi mencoba menghapus data mahasiswa lain yang hanya boleh dikelola oleh admin.

| Kondisi                                                     | Status yang sesuai |
| ----------------------------------------------------------- | ------------------ |
| Belum login ke endpoint yang memerlukan autentikasi         | 401 Unauthorized   |
| Token autentikasi tidak valid                               | 401 Unauthorized   |
| Sudah login tetapi tidak memiliki izin untuk fitur tersebut | 403 Forbidden      |

## 6. Kesimpulan

Authentication digunakan untuk memverifikasi identitas pengguna, sedangkan authorization digunakan untuk mengatur hak akses pengguna terhadap fitur atau sumber daya. Matriks role dan endpoint membantu menentukan tindakan yang boleh dilakukan setiap jenis pengguna. HTTP 401 digunakan ketika autentikasi belum valid, sedangkan HTTP 403 digunakan ketika pengguna terautentikasi tetapi tidak memiliki izin yang diperlukan.
