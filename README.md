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

# PRAKTIKUM 12 - Framework Lanjutan (CRUD)
- Jalankan `XAMPP`, buka `localhost` dan buat sebuah database seperti berikut
<img src=Praktikum12/1.png>
<img src=Praktikum12/2.png>

## Step 1 Konfigurasi Database
- Konfigurasi file `.env` ke database
<img src=Praktikum12/3.png>

## Step 2 Membuat Model
- Buat Artikel Model untuk memproses data Artikel. Buat file baru pada direktori `app/Models` dengan nama `ArtikelModel.php`
<img src=Praktikum12/4.png>

## Step 3 Membuat Controller
- Buat Controller baru dengan nama `Artikel.php` pada direktori `app/Controllers`
<img src=Praktikum12/5.png>

## Step 4 Membuat View
- Buat direktori baru dengan nama artikel pada direktori `app/views`, kemudian buat file baru dengan nama `index.php`. 
<img src=Praktikum12/5.5.png>

## Buka Lalu buka alamat `http://localhost:8080/artikel` untuk melihat hasilnya.
<img src=Praktikum12/6.png>
- Tidak ada data yang ditampilkan karena database masih kosong.

## Step 5 Menambahkan Artikel
<img src=Praktikum12/7.png>
- Hasilnya
<img src=Praktikum12/8.png>

## Step 6 Membuat Detail Artikel
- Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda. Tambahkan fungsi baru pada Controller Artikel dengan nama `view()`
<img src=Praktikum12/9.png>

## Step 7 Membuat View Detail
- Buat view baru untuk halaman detail dengan nama `app/views/artikel/detail.php`
<img src=Praktikum12/10.png>

## Step 8 Membuat Route
- Buka Kembali file `app/config/Routes.php`, kemudian tambahkan routing untuk artikel detail.
<img src=Praktikum12/11.png>

- Akses lagi `http://localhost:8080/artikel` dan klik salah satu artikel, hasilnya akan menjadi seperti ini.
<img src=Praktikum12/12.png>

## Step 9 Membuat Admin Menu
- Menu admin adalah untuk proses CRUD data artikel. Buat method baru pada Controller Artikel dengan nama `admin_index()`.
<img src=Praktikum12/13.png>

## Step 10 Membuat Tampilan Admin
- Selanjutnya buat view untuk tampilan admin dengan nama `admin_index.php`
<img src=Praktikum12/14.png>
<img src=Praktikum12/15.png>

## Step 11 Menambah Menu Routing Untuk Menu Admin
<img src=Praktikum12/16.png>

## Step 12 Mengakses Menu Admin
- Menu admin dapat diakses dengan alamat `http://localhost:8080/admin/artikel`
<img src=Praktikum12/17.png>

## Step 13 Menambah Menu Add Artikel
- Tambahkan fungsi/method baru pada Controller Artikel dengan nama `add()`.
<img src=Praktikum12/18.png>
- Kemudian buat view untuk form tambah dengan nama `form_add.php`
<img src=Praktikum12/18.5.png>
- Tampilannya seperti berikut
<img src=Praktikum12/19.png>

## Step 14 Menambah Menu Edit Artikel
- Tambahkan fungsi/method baru pada Controller Artikel dengan nama `edit()`. 
<img src=Praktikum12/19.5.png>
- Kemudian buat view untuk form tambah dengan nama `form_edit.php`
<img src=Praktikum12/19.5.1.png>
- Tampilannya seperti berikut
<img src=Praktikum12/20.png>

## Step 15 Menambah Menu Delete Artikel
- Tambahkan fungsi/method baru pada Controller Artikel dengan nama `delete()`.
<img src=Praktikum12/21.png>


# Pertanyaan dan Tugas
- Selesaikan programnya sesuai Langkah-langkah yang ada. Anda boleh melakukan improvisasi.

## Saya Sudah Melengkapi file `admin_header.php` dan `admin_footer.php` serta `CSS`nya agar programnya bisa di run.


- Admin_header.php
<img src=Praktikum12/q1.png>


- Admin_footer.php
<img src=Praktikum12/q2.png>


- Adminstyle.css
<img src=Praktikum12/q3.png>
<img src=Praktikum12/q4.png>


- Menambah Artikel Baru
<img src=Praktikum12/19.png>
<img src=Praktikum12/q5.png>
- Setelah menambahkan artikel, artikel ditambahkan dengan baik dan muncul di view nya.


- Menghapus Artikel
<img src=Praktikum12/q6.png>
<img src=Praktikum12/q7.png>
- Artikel berhasil dihapus

- Mengedit Artikel
<img src=Praktikum12/q8.png>
<img src=Praktikum12/q9.png>
- Artikel berhasil di edit


# PRAKTIKUM 13 `Pemrograman Web (Framework Lanjutan - Modul Login)`

## Step 1
- Persiapkan data untuk menu login di `phpmyadmin` dan buat tabel berikut :
<img src=Praktikum13/1.png>

## Step 2
- Membuat Model User dengan nama `UserModel.php` seperti berikut
<img src=Praktikum13/1.5.png>

## Step 3
- Membuat Control User dengan nama `User.php` , dan tambahkan method `index()` untuk menampilkan daftar user,
dan method `login()` untuk proses login.
<img src=Praktikum13/2.png>
<img src=Praktikum13/2.5.png>

## Step 4
- Membuat View Login, kita buat file baru di `view/user` kemudian buat `login.php`
<img src=Praktikum13/3.png>

## Step 5
- Membuat Database Seeder,  Buka CLI, kemudian tulis perintah berikut: `php spark make:seeder UserSeeder`. ini digunakan untuk mencoba module login kita perlu memasukkan data user dan password ke dalam database. Untuk itu buat database seeder untuk tabel user.
<img src=Praktikum13/4.png>
- Buka file UserSeeder.php yang berada di lokasi direktori `/app/Database/Seeds/UserSeeder.php` kemudian ikuti source code berikut:
<img src=Praktikum13/5.png>
- Buka CLI lagi dan ketik perintah : `php spark db:seed UserSeeder`
<img src=Praktikum13/6.png>
- Kemudian lakukan uji coba login dengan mengakses url : `http://localhost:8080/user/login`
<img src=Praktikum13/7.png>


## Step 6
- Buat file baru dengan nama Auth.php pada direktori `app/Filters` untuk memfilter halaman admin.
<img src=Praktikum13/8.png>
- Kemudian buka file `app/Config/Filters.php` tambahkan kode berikut:
<img src=Praktikum13/9.png>
- Lalu buka file `app/Config/Routes.php` dan sesuaikan kodenya seperti ini.
<img src=Praktikum13/10.png>
- Maka ketika mengakses alamat `http://localhost:8080/admin/artikel` akan dibawa ke halaman login.
<img src=Praktikum13/11.png>
- Hasil setelah login
<img src=Praktikum13/12.png>

## Step 7
- Membuat fungsi `logout`
<img src=Praktikum13/13.png>
<img src=Praktikum13/14.png>
- Hasil setelah menekan tombol log out
<img src=Praktikum13/15.png>


# Pertanyaan dan Tugas

## Selesaikan programnya sesuai Langkah-langkah yang ada. Anda boleh melakukan improvisasi.
- Program sudah saya selesaikan dari awal login hingga log out halaman admin, beserta css nya.
- `Route Log out`
<img src=Praktikum13/p1.png>
- `CSS`
<img src=Praktikum13/p2.png>



# PRAKTIKUM 14


## STEP 1
- Membuat Pagination
Pagination merupakan proses yang digunakan untuk membatasi tampilan yang panjang 
dari data yang banyak pada sebuah website. Fungsi pagination adalah memecah 
tampilan menjadi beberapa halaman tergantung banyaknya data yang akan ditampilkan 
pada setiap halaman. Untuk membuat pagination, buka Kembali Controller Artikel, kemudian modifikasi 
kode pada method admin_index seperti berikut.
<img src=Praktikum14/1.png>
- Kemudian buka file views/artikel/admin_index.php dan tambahkan kode berikut
dibawah deklarasi tabel data.
<img src=Praktikum14/2.png>
- Selanjutnya buka kembali menu daftar artikel, tambahkan data lagi untuk melihat 
hasilnya.
<img src=Praktikum14/3.png>


## STEP 2
- Membuat Pencarian
Pencarian data digunakan untuk memfilter data.
Untuk membuat pencarian data, buka kembali Controller Artikel, pada method 
admin_index ubah kodenya seperti berikut ;
<img src=Praktikum14/4.png>
- Kemudian buka kembali file views/artikel/admin_index.php dan tambahkan form 
pencarian sebelum deklarasi tabel seperti berikut:
<img src=Praktikum14/4.5.png>
- Dan ubah link pager menjadi `<?= $pager->only(['q'])->links(); ?>`
- Selanjutnya buka kembali halaman admin artikel dan masukkan kata kunci tertentu pada form pencarian.
<img src=Praktikum14/5.png>


## STEP 3
- Upload Gambar
Menambahkan fungsi unggah gambar pada tambah artikel. Buka kembali Controller 
Artikel, sesuaikan kode pada method add seperti berikut:
<img src=Praktikum14/6.png>
- Kemudian pada file views/artikel/form_add.php tambahkan field input file seperti 
berikut.
<img src=Praktikum14/7.png>
- Kemudian lakukan percobaan membuat artikel dengan mengupload sebuah gambar.
<img src=Praktikum14/8.png>
- Hasil yang telah di upload
<img src=Praktikum14/9.png>

```

Nama  : Ario Fajar
Kelas : TI.19.A2
NIM   : 311910610

````
