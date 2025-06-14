![Screenshot 2025-06-14 091517](https://github.com/user-attachments/assets/7c5a37b4-9f5d-4a06-b1da-d7910b34879a)# 💻 Praktikum PHP Framework (CodeIgniter 4)

Repositori ini berisi panduan praktikum untuk memahami dan menerapkan framework **CodeIgniter 4**, mulai dari pengenalan konsep dasar hingga membangun aplikasi sederhana dengan fitur **CRUD**.

---

# Praktikum 1

1. Mengaktifkan Ekstensi di

```bash
  php.ini
```

Berikut adalah ekstensi PHP yang harus diaktifkan:

1. php-json → Diperlukan untuk bekerja dengan JSON.
2. php-mysqlnd → Native driver untuk MySQL.
3. php-xml → Diperlukan untuk bekerja dengan XML.
4. php-intl → Diperlukan untuk mendukung aplikasi multibahasa.
5. libcurl (opsional) → Diperlukan jika ingin menggunakan Curl.

##

Buka xampp file Config

```bash
  php.ini
```

Pastikan ekstensi berikut tidak dikomentari (hilangkan tanda ; di depannya jika ada):

```bash
extension=json
extension=mysqli
extension=xml
extension=intl
extension=curl
```

![Hasil Serve](https://github.com/user-attachments/assets/7b776fc9-39ba-4606-95f4-3ee96a82859c)

## Instalasi

### 1. Instalasi CodeIgniter

Instalasi dengan cara manual:

1. Unduh CodeIgniter → (https://codeigniter.com/download)
2. Extrak file zip Codeigniter ke direktori htdocs/Lab7Web
3. Ubah nama direktory framework-4.x.xx menjadi ci4.
4. Menjalankan CLI XAMPP
   Arahkan direktori sesuai dengan project → (xampp/htdocs/Lab7Web/ci4/)
   Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah: php spark serve Meluncurkan server pengembangan bawaan, Memungkinkan melihat aplikasi di browser (http://localhost:8080).

### 2. Menjalankan CLI XAMPP

- Arahkan direktori sesuai dengan project → (xampp/htdocs/Lab7Web/ci4/)
- Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah: php spark serve Meluncurkan server pengembangan bawaan, Memungkinkan melihat aplikasi di browser (http://localhost:8080).

![Screenshot 2025-06-12 180638](https://github.com/user-attachments/assets/8f655722-403f-4b22-88c1-73a58ae0e353)
![Hasil Serve](https://github.com/user-attachments/assets/7b776fc9-39ba-4606-95f4-3ee96a82859c)

### 3. Mengaktifkan Mode Debugging

Fitur debugging dari CodeIgniter 4 untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. Mengaktifkan mode debugging dengan mengubah niai konfigurasi pada file
`env`, cari variable `CI_ENVIRONMENT` ubah menjadi `development`

![Debug Config](https://github.com/user-attachments/assets/d8d3827e-69f4-43eb-bff3-c11caffe17ff)

Kemudian rename nama file `env → .env`

Contoh Error yang terjadi ketika menghapus function pada file app/Controller/Home.php

![Error Sample](https://github.com/user-attachments/assets/def8f63d-ed58-4707-b2d4-d57d29815e5e)

![image](https://github.com/user-attachments/assets/33ba4c9c-e603-4854-a916-273b256e188c)


## 4. Routing dan Controllers

Routing dalam CodeIgniter 4 adalah proses yang menghubungkan permintaan (request) dari pengguna ke Controller yang sesuai untuk diproses. Routing ini memungkinkan kita menentukan bagaimana URL diterjemahkan menjadi aksi dalam aplikasi, sehingga setiap permintaan dapat diarahkan dengan benar.

#### Membuat Route baru (autoRoute(false)):

Secara default fitur autoRoute sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false. Nonaktifkan Auto Routing `($routes->setAutoRoute(false);)` ketika menjalankan di production.

tambahkan kode berikut dalam **app/Config/Routes.php**

![image](https://github.com/user-attachments/assets/47448e29-fbfa-4c8f-bfc6-d37e0c0e3c99)


Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah `php spark routes:`

![Route Output](https://github.com/user-attachments/assets/82bf7eeb-4988-42d4-ba21-1bf7f22f3ebc)


### Membuat Controllers:

tambahkan code berikut dalam **app/Controllers/Page.php**

#![Screenshot 2025-06-12 185420](https://github.com/user-attachments/assets/ee5eda62-a186-4150-b7e5-ab6ecb0a78d4)


### 5. Membuat View

1. Buat File app/Views/about.php dan ubah method about pada class Controller Page
2. Tambahkan code pada ke 4 file diatas:

![Screenshot 2025-06-12 185742](https://github.com/user-attachments/assets/c47167a6-5df6-40ba-9ae9-72522fc8f486)
![image](https://github.com/user-attachments/assets/00197742-46fb-4851-8b7b-7a98700d4ee8)


### 6. Membuat Layout

1. Buat direktori template pada direktori view kemudian buat file header.php dan footer.php Kemudian ubah file app/view/about.php seperti berikut.
   ![image](https://github.com/user-attachments/assets/adab12c9-e0df-4711-aec0-41ec74d49ab7)

   ![image](https://github.com/user-attachments/assets/95d03bd9-2a01-4c3d-ae7a-693a16696e0d)


2. buat di file `style.css` di dalam direktori public
   ![image](https://github.com/user-attachments/assets/62db5213-2d03-4423-b1a8-3fdaef9be076)


### 7. Hasil Output

![Screenshot 2025-06-14 084055](https://github.com/user-attachments/assets/bf4ec20a-285d-43c9-8540-59cfdc393640)


---


# Praktikum 2

### Membuat Database dan Tabel

![Screenshot 2025-06-14 084948](https://github.com/user-attachments/assets/b3cfa74d-52b6-44da-8365-1934d5b3a668)

### Config Koneksi Database

Lakukan Config untuk menghubungkan dengan database server pada file `.env`

![image](https://github.com/user-attachments/assets/88e40d4f-b893-4f83-b388-f6a1ea2ea2da)

### Membuat Artikel Model

Model ini menentukan hubungan antar data dan bagaimana data dapat diakses serta dimanipulasi. Membuat model untuk mengakses data artikel `app/Models`

![image](https://github.com/user-attachments/assets/2b739094-dcbe-49b4-9bc0-863ef848c402)


### Membuat Controller

Pada direktori `app/Controllers/Artikel.php` buat Controller pada func index

![image](https://github.com/user-attachments/assets/be2ebcc3-a881-42a2-bf8c-7a673938e66b)

### Tambahkan route untuk artikel Pada `Routes.php`

```routes
$routes->get('/artikel', 'Artikel::index');
```

### Membuat View 
Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file baru 
dengan nama index.php.  

![Screenshot 2025-06-14 091517](https://github.com/user-attachments/assets/87771180-43e4-4207-8421-5a5b0a25cdd2)



### Ubah `Home.php` menjadi

![App Screenshot](./screnshoot//16Ubahhome.php.png)

### Membuat Artikel Sementara di PHPMyAdmin

# ![App Screenshot](./screnshoot/17BuatArtikelSementara.png)

![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/14MembuatControllerHome.png)

### Buat Perubahan Kecil Pada `Routes.php`

![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/15RoutesPHP.png)

### Ubah `Home.php` menjadi

![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/16Ubahhome.php.png)

### Membuat Artikel Sementara di PHPMyAdmin

![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/17BuatArtikelSementara.png)

### Membuat Tampilan Detail Artikel

1. Ubah func Artikel pada `app/Controllers/Page.php`

   # ![App Screenshot](./screnshoot/18ubahFuncArtikel.png)

   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/18ubahFuncArtikel.png)

2. Membuat View baru di app/Views/artikel.php dan membuat routing baru di `app/Config/Routes.php`
   dan ubah dengan code
   **$routes->get('page/artikel/(:any)', 'Page::artikel/$1');**

   ![App Screenshot](./screnshoot/19buatartikel.phpViews.png)

3. Hasil
   ![App Screenshot](./screnshoot/20hasilDetailArtikel.png)

### Membuat Menu Admin

1.  Membuat Method baru pada Controllers `app/Controllers/Artikel.php` dengan nama **admin_index()**
    ![App Screenshot](./screnshoot/21MembuatControllerArtikel.php.png)

2.  Menuju direktori `app/Views` lalu buat **admin_index.php**
    ![App Screenshot](./screnshoot/22BuatAdminIndex.png)

3.  Tambah routes di `app/Config/Routes.php` untuk menu admin
    ![App Screenshot](./screnshoot/23TambahRoutes.php.png)

4.  Hasil Output
    ![App Screenshot](./screnshoot/25hasilAdmin.png)
    =======
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/19buatartikel.phpViews.png)

5.  Hasil
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/20hasilDetailArtikel.png)

### Membuat Menu Admin

1.  Membuat Method baru pada Controllers `app/Controllers/Artikel.php` dengan nama **admin_index()**
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/21MembuatControllerArtikel.php.png)
2.  Menuju direktori `app/Views` lalu buat **admin_index.php**
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/22BuatAdminIndex.png)

3.  Tambah routes di `app/Config/Routes.php` untuk menu admin
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/23TambahRoutes.php.png)

4.  Hasil Output
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/25HasilAdmin.png)

### Menambah Data Artikel

1. Menambah Func baru pada `app/Controllers/Artikel.php dengan **Add()**

   ![App Screenshot](./screnshoot/23TambahFungsiAdd.png)

2. Buat **add.php** di `app/Views` untuk form tambah artikel
   ![App Screenshot](./screnshoot/24BuatAdd.phpDiViews.png)

3. Hasil Output
   ![App Screenshot](./screnshoot/25hasilAdd.png)
   ![App Screenshot](./screnshoot/25HasilAdd1.png)
   =======
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/23TambahFungsiAdd.png)

4. Buat **add.php** di `app/Views` untuk form tambah artikel
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/24BuatAdd.phpDiViews.png)
5. Hasil Output
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/25hasilAdd.png)
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/25HasilAdd1.png)

### Edit Data

1. Menambahkan func baru pada `app/Controllers/Artikel.php` dengan nama **edit($id)**

   ![App Screenshot](./screnshoot/26EditPhp.png)

2. Buat `edit.php` di `app/Views` untuk form edit artikel
   ![App Screenshot](./screnshoot/26editphphtml.png)

3. Hasil Output
   ![App Screenshot](./screnshoot/25HasilEdit.png)
   =======
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/26EditPhp.png)

4. Buat `edit.php` di `app/Views` untuk form edit artikel
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/26editphphtml.png)

5. Hasil Output
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/25HasilEdit.png)

### Menghapus Data

1. Tambah Func baru pada `app/Controllers/Artikel.php` dengan nama **delete($id)**

   ![App Screenshot](./screnshoot/27DeletePHP.png)

2. Hasil Output "P" terhapus
   ![App Screenshot](./screnshoot/25HasilAdd1.png)
   ![App Screenshot](./screnshoot/25HasilDelete.png)
   =======
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/27DeletePHP.png)
3. Hasil Output "P" terhapus
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/25HasilAdd1.png)
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/25HasilDelete.png)

# Praktikum 3

### Membuat Class View Cell

Membuat Direktori Cells di dalam `app` lalu buat file `Artikel.php` pada `app/Cells`

# ![App Screenshot](./screnshoot/28aViewCels.png)

![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/28aViewCels.png)

### Membuat View untuk View Cells

1. Lakukan perubahan field pada database dengan menambahkan tanggal agar dapat mengambil data artikel terbaru

   ![App Screenshot](./screnshoot/29aMembuatdatabaru.png)

2. Buat folder component di `app/Views` yang didalamnya berisi `artikel_katgori.php & artikel_terkini.php`
   ![App Screenshot](./screnshoot/29bMembuatArtikelTerkini.png)
3. Isikan code di dalam file `artikel_terkini.php`
   ![App Screenshot](./screnshoot/29c.png)
4. Modifikasi `app/Views/layout/main.php`
   ![App Screenshot](./screnshoot/29dModifikasiLayout.png)
   =======
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/29aMembuatdatabaru.png)
5. Buat folder component di `app/Views` yang didalamnya berisi `artikel_katgori.php & artikel_terkini.php`
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/29bMembuatArtikelTerkini.png)
6. Isikan code di dalam file `artikel_terkini.php`
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/29c.png)
7. Modifikasi `app/Views/layout/main.php`
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/29dModifikasiLayout.png)

### Mengubah Views Cells agar Menampilkan Kategori tertentu

1. Menambahkan data baru / column baru untuk kategori

   ![App Screenshot](./screnshoot/29dMembuatColumnDataKategori.png)

2. Modifikasi model di `app/Models/ArtikelModel.php
   ![App Screenshot](./screnshoot/30aModifikasiArtikelMoels.png)
3. Membuat File `ArtikelKategori.php` baru pada folder `app/Cells`
   ![App Screenshot](./screnshoot/30cMembuatFileArtikelKategori.png)
4. Membuat file `artikel_kategori.php` baru pada folder `app/Views/components`.
   ![App Screenshot](./screnshoot/30dMembuatartikel_kategori.php.png)
5. Modifikasi code di file `app/Views/layout/main.php`
   ![App Screenshot](./screnshoot/30dModifLyout.php.png)
6. Tambahkan code berikut di file `app/Config/Routes.php`
   ![App Screenshot](./screnshoot/30eTambahRoutes.png)
7. Tambah Method kategori controller di `app/Controllers/Home.php`
   ![App Screenshot](./screnshoot/30fModifHome.php.png)
8. Hasil Output
   ![App Screenshot](./screnshoot/LASSTTTT.png)

   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/29dMembuatColumnDataKategori.png)

9. Modifikasi model di `app/Models/ArtikelModel.php
   ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/30aModifikasiArtikelMoels.png)
10. Membuat File `ArtikelKategori.php` baru pada folder `app/Cells`
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/30cMembuatFileArtikelKategori.png)
11. Membuat file `artikel_kategori.php` baru pada folder `app/Views/components`.
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/30dMembuatartikel_kategori.php.png)
12. Modifikasi code di file `app/Views/layout/main.php`
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/30dModifLyout.php.png)
13. Tambahkan code berikut di file `app/Config/Routes.php`
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/30eTambahRoutes.png)
14. Tambah Method kategori controller di `app/Controllers/Home.php`
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/30fModifHome.php.png)
15. Hasil Output
    ![image alt](https://github.com/ardhvka/Lab7web/blob/5c0754a252edb3a3fdab76d6dcb838fb5384336e/ci4/screnshoot/LASSTTTT.png)

# Praktikum 4

### Modul Login

1. Buat Table Baru
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/31a.BuatTabel.png)

2. Membuat Model User
   Buat file baru pada direktori `app/Models` dengan nama `UserModel.php`
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/31b.BuatModelUser.png)

3. Membuat Controller User
   Buat Controller baru dengan nama `User.php` pada direkdirektori app/Controllers. Kemudian tambahkan method **index()** untuk
   menampilkan daftar user dan method **login()** untuk proses login
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/31c.BuatUser.png)
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/31d.BuatUser2.png)

4. Membuat Halaman Login
   Buat direktori baru pada `app/Views` dengan nama `user` kemudian buat file di dalamnya dengan nama `login.php`
   lalu tambahkan code berikut ini
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/32a.BuatHalamanLogin.png)

5. Membuat Database Seeder
   Database seeder digunakan untuk membuat data dummy. Untuk keperluan ujicoba modul
   login, kita perlu memasukkan data user dan password kedaalam database. Untuk itu buat
   database seeder untuk tabel user. Buka CLI, kemudian tulis perintah berikut:

   **php spark make:seeder UserSeeder**

   Selanjutnya, buka file `UserSeeder.php` yang berada di lokasi direktori
   `/app/Database/Seeds/UserSeeder.php` kemudian isi dengan kode berikut:
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/32b.BuatDataSeeder.png)

   Selanjutnya buka kembali Terminal atau CLI dengan shortcut **ctrl+Shift+`** lalu ketikan perintah berikut

   `php spark db:seed UserSeeder`

   Lakukan uji coba login
   Buka url `http://localhost:8080/user/login`
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/33.Hasil.png)

6. Menambahkan Auth Filter
   Buat file untuk halaman admin dengan nama `Auth.php` pada `app/Filters` lalu isi kode ini
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/34a.TambahkanAuth.png)

7. Buka `app/Config/Filters.php` untuk menambahkan kode berikut ini
   ![image alt}](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/34b.TambahkanAuthPadaFilters.png)

8. Buka `app/Config/Routes.php` kemudian ubah routes menjadi seperti ini
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/35a.UbahRoutes.png)

9. Tambahkan Function Logout pada app/Controller/User.php
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/35b.TambahFuncLogout.png)

10. Hasil
    ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/33.Hasil.png)

# Praktikum 5

## Pagination & Search Bar

1. Buka `app/Controller/Artikel.php` untuk memodifikasi codingan berikut ini
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/35a.EditAdminIndex.png)

   Kemudian buka file views/artikel/admin_index.php dan tambahkan kode berikut dibawah deklarasi tabel data.

   `<?= $pager->links(); ?>`

2. Untuk membuat Search Bar buka kembali `app/Controller/Artikel.php` lalu modifikasi codingan berikut ini
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/35a.EditAdminIndex.png)

3. Buka `app/Views/artikel/admin_index.php` lalu tambahkan codingan berikut
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/38.tambahSearch.png)

4. Tambahkan link pager pada bagian bawah deklarasi tabel seperti berikut ini
   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/37.TambahPaginationDibawahHtml.png)

5. Hasil

   ![image alt](https://github.com/ardhvka/Lab7web/blob/013987ca6364b81a3ce063e03c6ce6119f1cd83f/ci4/screnshoot/36.Hasil.png)

# Praktikum 6

## Upload File Gambar

1. Buka direktori `app/Controller/Artikel.php` lalu edit code menjadi seperti ini

   ![image alt](https://github.com/ardhvka/Lab7web/blob/d60c04447806713984dd9488fbe12be5c1f83c03/ci4/screnshoot/39.TambahFuncGambar.png)

2. Lalu pada `app/Views/add.php` tambahkan kode berikut

   ![image alt](https://github.com/ardhvka/Lab7web/blob/d60c04447806713984dd9488fbe12be5c1f83c03/ci4/screnshoot/40.editAddphp.png)

   ![image alt](https://github.com/ardhvka/Lab7web/blob/d60c04447806713984dd9488fbe12be5c1f83c03/ci4/screnshoot/41.tambahKolomFormgambar.png)

3. Hasil

![image alt](https://github.com/ardhvka/Lab7web/blob/d60c04447806713984dd9488fbe12be5c1f83c03/ci4/screnshoot/42.Hasil1.png)

![image alt](https://github.com/ardhvka/Lab7web/blob/d60c04447806713984dd9488fbe12be5c1f83c03/ci4/screnshoot/42.Hasil2.png)

![image alt](https://github.com/ardhvka/Lab7web/blob/d60c04447806713984dd9488fbe12be5c1f83c03/ci4/screnshoot/43.Hasil3.png)

# Praktikum 7

### Membuat Tabel baru

![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax1.png)

### Relasi Antar Kategori

![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax2.png)

### Testing Sessions

1. Menampilkan Daftar Artikel
   ![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax3.png)
2. Pada Halaman Admin
   ![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax4.png)
   3.Menambahkan Artikel Baru dan Kategori Baru
   ![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax5.png)
3. Artikel Baru Berhasil Ditambahkan
   ![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax6.png)
4. Artikel dan Kategori baru berhasil tampil
   ![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax7.png)
   ![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax8.png)

# Praktikum 8

### Menambahkan Pustaka jQuery

![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax9.png)

### Membuat Ajax Controller

![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax10.png)

### Make View

![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax11.png)

### Make Routes

![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax12.png)

### Hasil

1. routes `$routes->get('admin/ajax', 'AjaxController::index');`
   ![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax13.png)

2. routes `$routes->get('ajax/getData', 'AjaxController::getData');`
   ![image alt](https://github.com/ardhvka/Lab7web/blob/bf2178571f69c16c72f39e08aee80e4311a7e4eb/ci4/screnshoot/ajax14.png)

# Praktikum 9

### Membuat Ajax Search Bar & Pagination

1. Edit Method _admin_index()_ seperti ini
   ![image alt](https://github.com/ardhvka/Lab7web/blob/0d8b3a144ca9f7719aa3dc1782baddd97558fd01/ci4/screnshoot/ajax15.png)

2. Edit file `admin_ajax.php` menjadi seperti ini
   ![image alt](https://github.com/ardhvka/Lab7web/blob/0d8b3a144ca9f7719aa3dc1782baddd97558fd01/ci4/screnshoot/ajax16.png)

3. Hasil
   ![image alt](https://github.com/ardhvka/Lab7web/blob/0d8b3a144ca9f7719aa3dc1782baddd97558fd01/ci4/screnshoot/ajax17.png)

   ![image alt](https://github.com/ardhvka/Lab7web/blob/0d8b3a144ca9f7719aa3dc1782baddd97558fd01/ci4/screnshoot/ajax18.png)


# Praktikum 10
### API
  1. Membuat file ``Post.php`` di ``app/Controller`` dengan code seperti ini
     
     ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api1.png)

  2. Menambahkan Routes 
  
  ``$routes->resource('post'); `` 
      ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api2.png)

  3.  ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api3.png)

## Testing Rest API 

  1. Buka aplikasi postman dan pilih create new → HTTP Request
     ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api4.png)
     
  2. Menampilkan Semua Data
     
     Pilih method GET dan masukkan URL berikut:
     http://localhost:8080/post

     lalu klik send
     ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api5.png)
     ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api6.png)

  3. Mengubah data
  
      Untuk mengubah data, silakan ganti method menjadi PUT. Kemudian, masukkan URL artikel
      yang ingin diubah. Misalnya, ingin mengubah data artikel dengan ID nomor 2, maka masukkan
      URL berikut:
     
      http://localhost:8080/post/1
     
      Selanjutnya, pilih tab Body. Kemudian, pilih x-www-form-uriencoded. Masukkan nama
      atribut tabel pada kolom KEY dan nilai data yang baru pada kolom VALUE. Kalau sudah,
      klik Send.

      ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api7.png)

     ### Berhasil Diubah

      ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api8.png)

  4. Menambah Data
     
      Anda perlu menggunakan method POST untuk menambahkan data baru ke database.
      Kemudian, masukkan URL berikut:
     
      http://localhost:8080/post
     
      Pilih tab Body, lalu pilih x-www-form-uriencoded. Masukkan atribut tabel pada kolom KEY
      dan nilai data baru di kolom VALUE. Jangan lupa, klik Send.
     
      ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api9.png)
     
     ### Berhasil Ditambahkan
     
      ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api9Hasil.png)

  5. Menghapus Data
      Pilih method DELETE untuk menghapus data. Lalu, masukkan URL spesifik data mana yang
      ingin di hapus. Misalnya, ingin menghapus data nomor 4, maka URL-nya seperti ini:
     
      http://localhost:8080/post/7
     
      Langsung Send

       ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api10.png)

      ### Berhasil Terhapus
     
      ![image alt](https://github.com/ardhvka/Lab7web/blob/20ff49b1683647fe53cb587cc9058cbb1412b2b6/screnshoot/Api10Hasil.png)









## 📘 Praktikum 1: Pengenalan CodeIgniter 4

### 🔧 Persiapan Awal

1. **Aktifkan ekstensi PHP** melalui file `php.ini` (XAMPP):
   ```ini
   extension=json
   extension=mysqli
   extension=xml
   extension=intl
   extension=curl
   ```

![Aktivasi Ekstensi](https://github.com/user-attachments/assets/cb47a03b-7932-4ba6-a008-24e36916b047)

---

### 📥 Instalasi CodeIgniter 4 (Manual)

1. **Unduh CodeIgniter 4**
   👉 [https://codeigniter.com/download](https://codeigniter.com/download)

2. **Ekstrak file ZIP** ke direktori:

   ```
   htdocs/Lab7Web
   ```

3. **Ubah nama folder** hasil ekstrak menjadi `ci4`.

---

### 💻 Menjalankan CLI via XAMPP

1. Buka Terminal / Command Prompt

2. Arahkan direktori ke:

   ```bash
   cd xampp/htdocs/Lab7Web/ci4
   ```

3. Jalankan server:

   ```bash
   php spark serve
   ```

Akses browser: [http://localhost:8080/](http://localhost:8080/)
![Hasil Serve](https://github.com/user-attachments/assets/7b776fc9-39ba-4606-95f4-3ee96a82859c)

---

### 🐞 Mengaktifkan Mode Debugging

1. **Ubah environment menjadi development**
   Di file `env`, ubah:

   ```ini
   CI_ENVIRONMENT = production
   ```

   menjadi:

   ```ini
   CI_ENVIRONMENT = development
   ```

2. **Rename file `env` → `.env`**

   ![Debug Config](https://github.com/user-attachments/assets/d8d3827e-69f4-43eb-bff3-c11caffe17ff)

Contoh error jika function `index()` dihapus:
![Error Sample](https://github.com/user-attachments/assets/def8f63d-ed58-4707-b2d4-d57d29815e5e)

---

### 🌐 Routing dan Controller

#### 📌 Auto Routing

Auto Routing memetakan URL otomatis ke controller. Namun fitur ini **tidak direkomendasikan untuk production**.

Untuk menonaktifkannya:

```php
// app/Config/Routes.php
$routes->setAutoRoute(false);
```

---

### ✏️ Membuat Route Baru

Tambahkan pada `Routes.php`:

```php
$routes->get('/about', 'Page::about'); 
$routes->get('/contact', 'Page::contact'); 
$routes->get('/faqs', 'Page::faqs');
```

Cek routes via terminal:

```bash
php spark routes
```

![Route Output](https://github.com/user-attachments/assets/82bf7eeb-4988-42d4-ba21-1bf7f22f3ebc)

---

### 📂 Membuat Controller `Page.php`

Letakkan di `app/Controllers`

![Page Controller](https://github.com/user-attachments/assets/7318a866-971f-472b-a43d-7884b4bf5058)

---

### 🖼 Membuat View

1. Buat file `about.php` di `app/Views`
   
![About View](https://github.com/user-attachments/assets/944e3b34-caec-4035-8392-4552c3b337a2)

3. Update method `about()` di controller:
![Method Update](https://github.com/user-attachments/assets/fce21bf7-1b67-4fd0-8b25-ac5b26e5473a)

4. Buka di browser: [http://localhost:8080/about](http://localhost:8080/about)
![About Page](https://github.com/user-attachments/assets/41d2187d-e297-4f4c-8fee-030bd9e6bce4)

---

### 🧩 Menambahkan Template Layout

1. Buat folder `template` di `app/Views`

2. Tambahkan `header.php` dan `footer.php`
   ![Header](https://github.com/user-attachments/assets/27989420-6f2a-4a27-b95b-b470bbebdab5)
   ![Footer](https://github.com/user-attachments/assets/72c13407-bfb9-4ac6-94bf-0f092c40e723)

3. Gunakan layout ini di `about.php`:
   
   ![About + Layout](https://github.com/user-attachments/assets/ea3b96cd-5074-460d-b684-1e76314f3012)

5. Tambahkan CSS agar tampilan lebih menarik
   ![Final UI](https://github.com/user-attachments/assets/b712be94-0d75-4a68-81bb-3cc55faf35e5)

---

## 📗 Praktikum 2: Framework Lanjutan – CRUD dengan CodeIgniter 4

Panduan ini membahas cara membangun aplikasi **CRUD (Create, Read, Update, Delete)** menggunakan CodeIgniter 4.

---

### 🧱 1. Membuat Database

Buat database `lab_ci4`, lalu tabel `artikel`:
![DB Structure](https://github.com/user-attachments/assets/d811098b-ecdb-472e-8553-684b1d9c380c)

---

### ⚙️ 2. Konfigurasi Koneksi Database

Edit file `.env`:

![DB Config](https://github.com/user-attachments/assets/3015f8ec-7cbc-4e58-8b1c-c1f3de1462d5)

---

### 🧩 3. Membuat Model

Buat `ArtikelModel.php` di `app/Models`

![Model](https://github.com/user-attachments/assets/d5e447f1-755d-4a25-a83a-e686f103cb32)

---

### 🧭 4. Membuat Controller `Artikel.php`

Letakkan di `app/Controllers`
![Controller](https://github.com/user-attachments/assets/d7859c41-a68d-4e09-a79c-654442de8041)

---

### 🖼️ 5. Membuat View `index.php`

Letakkan di `app/Views/artikel`
![View Index](https://github.com/user-attachments/assets/3dbc2eb7-d4af-46cd-8e20-f052d13a3346)

---

### 🌐 6. Menampilkan Artikel di Browser

Akses: [http://localhost:8080/artikel](http://localhost:8080/artikel)
![View Result](https://github.com/user-attachments/assets/390ca551-d370-47bf-b625-1d2bcca669ca)

---

### ✍️ 7. Menambahkan Data Artikel

Isi database agar artikel dapat ditampilkan
![Input Data](https://github.com/user-attachments/assets/b144d6a1-abbb-424a-8763-ce0a4af637d9)
![Hasil Data](https://github.com/user-attachments/assets/856c63dc-962a-46a1-88a2-38d10b077344)

---

### 🔍 8. Detail Artikel (Routing Dinamis)

Klik judul artikel akan membuka halaman detail:
![Detail View](https://github.com/user-attachments/assets/5033d25b-7306-4ef8-8ec2-949406dc870d)

---

### 🧑‍💼 9. Menu Admin

Tambahkan method `admin_index()` dan view `admin_index.php`
![Admin View](https://github.com/user-attachments/assets/37e9840f-f110-424f-a0e9-1d0aa6ef32bc)

---

### ➕ 10. Tambah Data (Admin)

Form untuk input artikel baru:
![Tambah Data](https://github.com/user-attachments/assets/9c03bb51-791f-4c7d-99b4-6b083c9a1b87)

---

### ✏️ 11. Edit Data

Form edit data artikel:
![Edit](https://github.com/user-attachments/assets/bb4e84ec-e671-4c53-b5eb-cd45104709d4)

---

### 🗑️ 12. Hapus Data

Fungsi hapus data artikel:
![Hapus]\([https://github.com/user-attachments/assets/fbb28377-eddc-4dd1-9fc4-116](https://github.com/user-attachments/assets/fbb28377-eddc-4dd1-9fc4-116)
