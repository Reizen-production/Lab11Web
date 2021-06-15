# Lab11Web
# Praktikum 11 - Pemrograman Web (PHP Framework-CodeIgniter)
## Mengaktifkan Ekstensi
- Kita harus mengaktifkan beberapa ekstension diantaranya :
- `php-json` ekstension untuk bekerja dengan JSON;
- `php-mysqlnd` native driver untuk MySQL;
- `php-xml` ekstension untuk bekerja dengan XML;
- `php-intl` ekstensi untuk membuat aplikasi multibahasa;
- `libcurl` (opsional), jika ingin pakai Curl


- Mengaktifkan ekstension dengan cara klik config pada `Apache`, kemudian pilih `php.ini`
<img src=Praktikum11/0.png>

- Kemudian aktifkan ekstension dengan cara menghapus tanda `;` pada line 922, pilih ekstension yang akan diaktifkan
<img src=Praktikum11/1.png>

## Menginstal `CodeIgniter`
- Unduh Codeigniter dari website `https://codeigniter.com/download`
<img src=Praktikum11/2.png>
- Extrak file zip Codeigniter ke direktori `htdocs/lab11_ci`
<img src=Praktikum11/3.png>
- Ubah nama direktory `framework-4.x.xx` menjadi `ci4`
- Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/
<img src=Praktikum11/4.png>

## Menjalankan `CLI (Command Line Interface)`
- Codeigniter 4 menyediakan CLI untuk mempermudah proses development. 
- Untuk mengakses CLI buka `terminal/command prompt` lalu jalankan `php spark`
<img src=Praktikum11/5.png>

- Tidak seperti di panduan, saya tidak menemukan error
<img src=Praktikum11/6.png>

- Agar Localhost:8080 dapat diakses, gunakan perintah `php spark serve`
<img src=Praktikum11/7.png>

## Mengaktifkan Mode Debugging
- Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi 
pada environment variable `CI_ENVIRINMENT` menjadi `development`. jangan lupa untuk ubah nama file `env` menjadi `.env`
<img src=Praktikum11/8.png>
- Karena saya tidak mendapatkan ParseError, saya melanjutkan prosesnya


## Membuat Route
- Tambahkan kode berikut di dalam `Routes.php`
<img src=Praktikum11/12.png>
- Untuk mengecek Route kita sudah berjalan atau belum, gunakan perintah `php spark routes` pada `cmd`
<img src=Praktikum11/13.png>

## Akses Route
- Setelah membuat route, saya akan mengakses  `http://localhost:8080/about` dan ini yang terjadi
<img src=Praktikum11/14.png>

## Membuat Controller
- Buatlah `page.php` di dalam direktori controller `/app/Controller`
<img src=Praktikum11/15.png>
- Hasil nya akan seperti berikut setelah merefresh page nya
<img src=Praktikum11/16.png>

## Membuat Method Baru Pada Controller Page
<img src=Praktikum11/17.png>

## Membuat View
- Buat file `about.php` di dalam direktori view `app/view/about.php`
<img src=Praktikum11/18.png>
- Ubah method dalam controller page
<img src=Praktikum11/19.png>
- Hasilnya seperti berikut 
<img src=Praktikum11/20.png>

## Membuat Layout Web dengan CSS
- Copy `style css` dari `lab4web` yang telah dibuat ke direktori `public`
- Kemudian buat direktori `template` pada direktori `view`, lalu buat `header.php` dan `footer.php`
<img src=Praktikum11/21.png>
<img src=Praktikum11/22.png>
- Kemudian ubah file `about.php` seperti berikut


```
<?= $this->include('template/header'); ?>
<h1><?= $title; ?></h1>
<hr>
<p><?= $content; ?></p>
<?= $this->include('template/footer'); ?>

```


- Refresh browser, kemudian hasilnya akan seperti berikut :
<img src=Praktikum11/23.png>


# Pertanyaan dan Tugas

```
Lengkapi kode program untuk menu lainnya yang ada pada Controller Page,
sehingga semua link pada navigasi header dapat menampilkan tampilan dengan layout yang sama.

```

## Hasil Tugas
<img src=Praktikum11/T1.png>

<img src=Praktikum11/T2.png>

<img src=Praktikum11/T3.png>
