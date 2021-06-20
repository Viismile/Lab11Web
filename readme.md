# Praktikum 11 - Pemrograman Web (PHP Framework)

```
Rofi Ismail - 311910657
TI.19.A.2
```

## Laporan Praktikum
### Persiapan
Mengaktifkan beberapa ekstensi php, diantaranya:
- php-json ekstension untuk bekerja dengan JSON;
- php-mysqlnd native driver untuk MySQL;
- php-xml ekstension untuk bekerja dengan XML;
- php-intl ekstensi untuk membuat aplikasi multibahasa;
- libcurl (opsional), jika ingin pakai Curl</br>
![SS1](https://user-images.githubusercontent.com/56240078/121922151-e2797880-cd63-11eb-89dc-766aa9fcfd33.jpg)

Hapus tanda ; (titik koma) pada bagian extension yang akan diaktifkan.
![SS2](https://user-images.githubusercontent.com/56240078/121922158-e5746900-cd63-11eb-8972-da921b23e9a5.jpg)

## Instalasi CodeIgniter 4
- Codeigniter dapat didownload dari website https://codeigniter.com/download
- Extrak file zip Codeigniter ke direktori htdocs/lab11_php_ci.
- Ubah nama direktory framework-4.x.xx menjadi ci4.
- Buka browser dengan alamat http://localhost/lab11_php_ci/ci4/public/
![SS3](https://user-images.githubusercontent.com/56240078/121922164-e60cff80-cd63-11eb-80ba-4193645e1199.jpg)

<br>Codeigniter menyediakan CLI, untuk mengaksesnya buka terminal lalu arahkan ke direktori project yang akan dibuat. Kemudian jalankan perintah `php spark` untuk memanggil CLI codeigniter.
![SS4](https://user-images.githubusercontent.com/56240078/121922165-e73e2c80-cd63-11eb-9298-c06a2b3e1a02.jpg)

<br>Codeigniter juga menyediakan mode debugging/development yang dapat menampilkan error/kesalahan dalam kode program. Cara mengaktifkannya dengan mengubah nama file `env` menjadi `.env` kemudian buka filenya dan ubah nilai <b>CI_ENVIRONMENT</b> menjadi <b>development</b>.
![SS5](https://user-images.githubusercontent.com/56240078/121922168-e7d6c300-cd63-11eb-8b2b-bc6027b9f95f.jpg)

<br>Maka pesan kesalahan akan ditampilkan.
![SS6](https://user-images.githubusercontent.com/56240078/121922172-e907f000-cd63-11eb-848f-d6df5ad8bf2b.jpg)

### Langkah 1 - Membuat Route
- Router terletak pada file app/config/Routes.php
- Untuk mengetahui route yg ada atau telah berjalan dapat menggunakan perintah `php spark routes`
![SS18](https://user-images.githubusercontent.com/56240078/121931730-338e6a00-cd6e-11eb-8fd0-32d16a64b795.jpg)

- Selanjutnya mencoba akses route yang telah dibuat dengan mengakses 
http://localhost:8080/contact
- Terjadi error file not found dikarenakan tidak ada file/page untuk halaman contact.
![SS7](https://user-images.githubusercontent.com/56240078/121922177-e9a08680-cd63-11eb-9826-944744a16c70.jpg)

### Langkah 2 - Membuat Controller
- Membuat file <b>page.php</b> di dalam direktori Controller (/app/Controllers)
![SS19](https://user-images.githubusercontent.com/56240078/121932746-6c7b0e80-cd6f-11eb-877b-31afa59fd6dd.jpg)

- Kemudian refresh browser maka halaman sudah dapat diakses dan menampilkan hasilnya.
![SS8](https://user-images.githubusercontent.com/56240078/121922179-ea391d00-cd63-11eb-8169-a7faa174c007.jpg)

- Menambahkan method baru pada controller page.
- Method ini dapat diakses dengan menggunakan alamat: http://localhost:8080/page/tos
![SS10](https://user-images.githubusercontent.com/56240078/121922185-eb6a4a00-cd63-11eb-835f-a730e4ee85f2.jpg)

### Langkah 3 - Membuat View
- Membuat file <b>about.php</b> di dalam direktori View (/app/view/about.php)
![SS11](https://user-images.githubusercontent.com/56240078/121922188-ec02e080-cd63-11eb-861c-cbda673bcf13.jpg)

- Mengubah method about dalam controller page.
![SS12](https://user-images.githubusercontent.com/56240078/121922190-ec9b7700-cd63-11eb-8486-1e2ff02e4fb9.jpg)

- Maka akan tampil seperti ini
![SS13](https://user-images.githubusercontent.com/56240078/121922195-ed340d80-cd63-11eb-9f54-9e41e41b2f5b.jpg)

### Langkah 4 - Membuat Layout Web dengan CSS
- Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout).
![SS14](https://user-images.githubusercontent.com/56240078/121922198-edcca400-cd63-11eb-8f07-4a4637830d0f.jpg)

- Kemudian buat folder template pada direktori view, lalu buat file <b>header.php</b> dan <b>footer.php</b>.
![SS15](https://user-images.githubusercontent.com/56240078/121922201-ee653a80-cd63-11eb-9975-ddc0f966dd7f.jpg)
![SS16](https://user-images.githubusercontent.com/56240078/121922205-eefdd100-cd63-11eb-9862-78897dd1c96e.jpg)

- Kemudian ubah file about.php (/app/view/about.php) seperti berikut.
```
<?= $this->include('template/header'); ?>
<h1><?= $title; ?></h1>
<hr>
<p><?= $content; ?></p>
<?= $this->include('template/footer'); ?>
```

- Kemudian refresh browser atau akses alamat http://localhost:8080/about
![SS17](https://user-images.githubusercontent.com/56240078/121922212-f02efe00-cd63-11eb-9791-b8b11bca032d.jpg)

## Pertanyaan dan Tugas
Lengkapi kode program untuk menu lainnya yang ada pada Controller Page, sehingga semua link pada navigasi header dapat menampilkan tampilan dengan layout yang sama.

## Hasil tugas
- Tampilan page about
![SS-About](https://user-images.githubusercontent.com/56240078/121922214-f0c79480-cd63-11eb-864f-ac533acfa4d0.jpg)

- Tampilan page artikel
![SS-Artikel](https://user-images.githubusercontent.com/56240078/121922215-f1602b00-cd63-11eb-839a-72438252fe4e.jpg)

- Tampilan page kontak
![SS-Kontak](https://user-images.githubusercontent.com/56240078/121922219-f1f8c180-cd63-11eb-961b-0af854c22400.jpg)

</br>

# Praktikum 12 - Pemrograman Web (Framework Lanjutan - CRUD)

```
Rofi Ismail - 311910657
TI.19.A.2
```

## Laporan Praktikum
### Persiapan
Pastikan MySQL server sudah berjalan dan buat sebuah database sebagai berikut:
![SS1](https://user-images.githubusercontent.com/56240078/122239924-8e010500-ceeb-11eb-8cc9-b2989a70becd.jpg)

### Langkah 1 - Konfigurasi Database
Membuat konfigurasi hubungan ke database server dengan menggunakan file `.env`.
![SS2](https://user-images.githubusercontent.com/56240078/122239933-8fcac880-ceeb-11eb-8a6b-c1af80925afc.jpg)

### Langkah 2 - Membuat Model
Buat file baru pada direktori /app/Models dengan nama ArtikelModel.php
![SS3](https://user-images.githubusercontent.com/56240078/122239934-90635f00-ceeb-11eb-87ca-bd4575ac3cc8.jpg)

### Langkah 3 - Membuat Controller
Buat Controller baru dengan nama Artikel.php pada direktori /app/Controllers. 
![SS4](https://user-images.githubusercontent.com/56240078/122239941-90635f00-ceeb-11eb-9726-37f94fe89797.jpg)

### Langkah 4 - Membuat View
Buat direktori baru dengan nama <b>artikel</b> pada direktori /app/Views, kemudian buat file baru dengan nama <b>index.php</b>.
![SS5](https://user-images.githubusercontent.com/56240078/122239946-90fbf580-ceeb-11eb-9b89-68abd605d7ff.jpg)
Lalu buka alamat http://localhost:8080/artikel untuk melihat hasilnya.

Tidak ada data yang ditampilkan karena database masih kosong.
![SS6](https://user-images.githubusercontent.com/56240078/122239949-91948c00-ceeb-11eb-90a0-07c14f4be8d0.jpg)

Tambahkan data pada database untuk ditampilkan datanya.
![SS7](https://user-images.githubusercontent.com/56240078/122239956-922d2280-ceeb-11eb-9e0a-55bc2560c78f.jpg)

Maka akan muncul tampilan seperti ini ketika browser direfresh.
![SS8](https://user-images.githubusercontent.com/56240078/122239958-935e4f80-ceeb-11eb-85f6-add8dce9ad09.jpg)

### Langkah 5 - Membuat Tampilan Detail Artikel
Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda.
Tambahkan sebuah fungsi baru pada <b>Controller Artikel</b> (/app/Controllers/Artikel.php) dengan nama <b>view()</b>.
![SS9](https://user-images.githubusercontent.com/56240078/122239959-935e4f80-ceeb-11eb-8bc7-2bd4b1e164bc.jpg)

### Langkah 6 - Membuat View Detail
Buat file baru dalam folder artikel <b>(/app/Views/artikel/)</b> dengan nama <b>detail.php</b> untuk menampilkan halaman detail.
![SS10](https://user-images.githubusercontent.com/56240078/122239961-93f6e600-ceeb-11eb-9b0b-8bb7db7968c8.jpg)

### Langkah 7 - Membuat Route
Buka file <b>Routes.php</b> dalam folder <b>(/app/Config/)</b> dan tambahkan routing untuk ke halaman detail artikel.</br>
`$routes->get('/artikel/(:any)', 'Artikel::view/$1');`
![SS11](https://user-images.githubusercontent.com/56240078/122239965-948f7c80-ceeb-11eb-96e6-f767fa26bce8.jpg)

Maka akan tampil halaman dari artikel yang diklik.
![SS12](https://user-images.githubusercontent.com/56240078/122239967-95281300-ceeb-11eb-9fe0-9e056ccc1db1.jpg)

### Langkah 8 - Membuat Menu Admin
Menu admin adalah untuk proses CRUD data artikel.</br>
Buat method atau fungsi baru pada <b>Controller Artikel</b> dengan nama <b>admin_index()</b>.
![SS13](https://user-images.githubusercontent.com/56240078/122239972-95c0a980-ceeb-11eb-8aba-7fb4a9c56a09.jpg)

Kemudian buat file <b>admin_index.php</b> dalam folder <b>(/app/Views/artikel/)</b> untuk tampilan halaman admin.
![SS14](https://user-images.githubusercontent.com/56240078/122239974-95c0a980-ceeb-11eb-97a7-47d1caa5ddd9.jpg)

Kemudian tambahkan routing untuk menu admin sebagai berikut:
![SS23](https://user-images.githubusercontent.com/56240078/122246380-b2abab80-cef0-11eb-8082-8fd4940c390a.jpg)

Menu admin dapat diakses dengan alamat http://localhost:8080/admin/artikel
![SS15](https://user-images.githubusercontent.com/56240078/122239979-96594000-ceeb-11eb-9c84-deeeee79ce21.jpg)

### Langkah 9 - Menambah Data Artikel
Tambahkan fungsi/method baru pada <b>Controller Artikel</b> dengan nama <b>add()</b>.
![SS16](https://user-images.githubusercontent.com/56240078/122239982-96f1d680-ceeb-11eb-9f7f-3651f57e9431.jpg)

Kemudian buat view untuk form tambah dengan nama <b>form_add.php</b> dalam folder <b>(/app/Views/artikel/)</b>.
![SS17](https://user-images.githubusercontent.com/56240078/122239986-978a6d00-ceeb-11eb-927b-029f5d5c61b7.jpg)

Tampilannya kurang lebih akan seperti ini.
![SS18](https://user-images.githubusercontent.com/56240078/122239988-98230380-ceeb-11eb-88a0-74915c513512.jpg)

### Langkah 10 - Mengubah Data
Tambahkan fungsi/method baru pada <b>Controller Artikel</b> dengan nama <b>edit()</b>.
![SS19](https://user-images.githubusercontent.com/56240078/122239990-98bb9a00-ceeb-11eb-9930-89600fddaaed.jpg)

Kemudian buat view untuk form tambah dengan nama <b>form_edit.php</b> dalam folder <b>(/app/Views/artikel/)</b>.
![SS20](https://user-images.githubusercontent.com/56240078/122239992-99543080-ceeb-11eb-81b5-ad681d379be8.jpg)

Kurang lebih tampilannya akan seperti ini ketika ingin mengubah data atau isi artikel.
![SS21](https://user-images.githubusercontent.com/56240078/122239993-99543080-ceeb-11eb-8533-767a87fa3ab6.jpg)

### Langkah 11 - Menghapus Data
Tambahkan fungsi/method baru pada <b>Controller Artikel</b> dengan nama <b>delete()</b>.
![SS22](https://user-images.githubusercontent.com/56240078/122239995-99ecc700-ceeb-11eb-89f6-9fc17f9a256e.jpg)

## Pertanyaan dan Tugas
Selesaikan programnya sesuai Langkah-langkah yang ada. Anda boleh melakukan improvisasi.

## Jawab/Hasil
Saya telah menyelesaikan program diatas agar dapat berjalan dengan semestinya. Seperti membuat file <b>admin_header.php</b> dan <b>admin_footer.php</b> serta CSSnya.

### Screenshot
- Admin_header.php
![Admin_Head](https://user-images.githubusercontent.com/56240078/122661690-30084200-d1b7-11eb-90ab-068d45718162.jpg)

- Admin_footer.php
![Admin_Footer](https://user-images.githubusercontent.com/56240078/122661689-2e3e7e80-d1b7-11eb-82c6-aec936cc57bf.jpg)

- Sebagian style untuk bagian admin.
![Admin_Style](https://user-images.githubusercontent.com/56240078/122661691-30a0d880-d1b7-11eb-9c9a-c1e27927df80.jpg)

- Menambahkan artikel baru
![Tambah_Artikel](https://user-images.githubusercontent.com/56240078/122661698-339bc900-d1b7-11eb-9183-2cd684a3ad8d.jpg)
![Tambah_Artikel2](https://user-images.githubusercontent.com/56240078/122661699-34345f80-d1b7-11eb-8085-5037ec630901.jpg)

- Menghapus artikel
![Hapus_Artikel](https://user-images.githubusercontent.com/56240078/122661695-326a9c00-d1b7-11eb-857d-10969506acee.jpg)
![Hapus_Artikel2](https://user-images.githubusercontent.com/56240078/122661697-33033280-d1b7-11eb-9384-ffdb646f1f91.jpg)

- Mengedit artikel
![Edit_Artikel](https://user-images.githubusercontent.com/56240078/122661692-31396f00-d1b7-11eb-8bac-ff079f39d152.jpg)
![Edit_Artikel2](https://user-images.githubusercontent.com/56240078/122661694-31d20580-d1b7-11eb-954f-8e8a2074f838.jpg)

