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
