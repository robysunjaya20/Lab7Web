# Praktikum PHP Framework (CodeIgniter 4)

## 📌 Praktikum 1: Pengenalan CodeIgniter 4

### Persiapan Awal
1. Aktifkan ekstensi PHP di `php.ini` (pada XAMPP):
   ```ini
   extension=json
   extension=mysqli
   extension=xml
   extension=intl
   extension=curl

![image](https://github.com/user-attachments/assets/cb47a03b-7932-4ba6-a008-24e36916b047)

### 1. Instalasi CodeIgniter

Langkah-langkah instalasi CodeIgniter secara manual:

1. **Unduh CodeIgniter**  
   Kunjungi situs resmi CodeIgniter:  
   👉 [https://codeigniter.com/download](https://codeigniter.com/download)

2. **Ekstrak File Zip**  
   Ekstrak hasil unduhan ke direktori htdocs/Lab7Web

3. **Ubah Nama Direktori**  
Ganti nama folder hasil ekstraksi (contoh: `CodeIgniter-4.x.x`) menjadi: ci4

---

### 2. Menjalankan CLI via XAMPP

1. **Buka Terminal / Command Prompt**
2. **Arahkan ke Direktori Proyek**
```bash
cd xampp/htdocs/Lab7Web/ci4

```
3. ** Lalu masukan perintah: php spark serve

sehingga saat kita mengakses http://localhost:8080/ pada browser menampilkan
![Screenshot 2025-03-21 235111](https://github.com/user-attachments/assets/7b776fc9-39ba-4606-95f4-3ee96a82859c)

### 3. Mengaktifkan Mode Debugging

CodeIgniter 4 menyediakan **fitur debugging** untuk membantu developer melihat detail pesan error saat terjadi kesalahan dalam kode program.

#### Langkah-langkah Mengaktifkan Debug Mode:

1. **Ubah Konfigurasi Environment**
   - Buka file `env` yang ada di root project.
   - Cari baris berikut:
     ```ini
     CI_ENVIRONMENT = production
     ```
   - Ubah menjadi:
     ```ini
     CI_ENVIRONMENT = development
     ```
![image](https://github.com/user-attachments/assets/d8d3827e-69f4-43eb-bff3-c11caffe17ff)

2. **Rename File `env`**
   - Ganti nama file `env` menjadi `.env`

#### Contoh Error

Jika terjadi kesalahan seperti **menghapus function `index()` pada file**:
![Screenshot 2025-03-22 000029](https://github.com/user-attachments/assets/def8f63d-ed58-4707-b2d4-d57d29815e5e)

## Routing dan Controllers

Routing dalam **CodeIgniter 4** adalah proses menghubungkan URL (permintaan pengguna) ke **controller dan method** tertentu. Routing memungkinkan kita mengatur bagaimana URL ditangani dan diarahkan ke aksi yang sesuai dalam aplikasi.

### Mengatur Routing (Auto Routing)

Secara default, CodeIgniter 4 mengaktifkan **Auto Routing** yang memungkinkan URL dipetakan otomatis ke controller. Namun **Auto Routing sangat tidak disarankan untuk production** karena bisa menyebabkan celah keamanan.

#### Menonaktifkan Auto Routing

Untuk menonaktifkannya, buka file: app/Config/Routes.php 
Kemudian ubah atau tambahkan baris berikut:
```php
$routes->setAutoRoute(false);
```

### Membuat Route baru
Langkah-langkah membuatnya
1. Buat route Tambahkan kode berikut di dalam Routes.php 
   ```php
   $routes->get('/about', 'Page::about'); 
   $routes->get('/contact', 'Page::contact'); 
   $routes->get('/faqs', 'Page::faqs');
   ```
   
Jika berhasil saat ketik php spark routes pada CMD menampilkan:
![Screenshot 2025-03-22 000409](https://github.com/user-attachments/assets/82bf7eeb-4988-42d4-ba21-1bf7f22f3ebc)

2. Buat Controller pada directory Controller
Buat file page.php kemudian isi kodenya seperti berikut.

   ![image](https://github.com/user-attachments/assets/7318a866-971f-472b-a43d-7884b4bf5058)

Setelah itu saat kita membuka http://localhost:8080/about akan menampilkan
![Screenshot 2025-03-22 001349](https://github.com/user-attachments/assets/68f154bd-58bd-4cb7-9d18-fcfb1612454c)

4. buat View 
Buat file baru dengan nama about.php pada direktori view (app/view/about.php) kemudian isi kodenya seperti berikut.
![image](https://github.com/user-attachments/assets/944e3b34-caec-4035-8392-4552c3b337a2)

dan ubah method about pada class Controller Page menjadi seperti berikut:
![image](https://github.com/user-attachments/assets/fce21bf7-1b67-4fd0-8b25-ac5b26e5473a)

Kemudian refrest http://localhost:8080/about dan akan menampilkan
![image](https://github.com/user-attachments/assets/41d2187d-e297-4f4c-8fee-030bd9e6bce4)

3. buat folder template pada direktori view kemudian buat file header.php dan footer.php
   ![image](https://github.com/user-attachments/assets/27989420-6f2a-4a27-b95b-b470bbebdab5)
   ![image](https://github.com/user-attachments/assets/72c13407-bfb9-4ac6-94bf-0f092c40e723)
    Kemudian ubah file app/view/about.php
   ![image](https://github.com/user-attachments/assets/ea3b96cd-5074-460d-b684-1e76314f3012)

Kemudian tambahkan css sehingga menampilkan
![Screenshot 2025-03-22 002113](https://github.com/user-attachments/assets/b712be94-0d75-4a68-81bb-3cc55faf35e5)


Praktikum 2: Framework Lanjutan (CRUD)
1. Buat database dengan nama lab_ci4, kemudian buat tabel dengan nama artikel
![image](https://github.com/user-attachments/assets/d811098b-ecdb-472e-8553-684b1d9c380c)
2. Konfigurasi koneksi database pada fie .env
   ![image](https://github.com/user-attachments/assets/3015f8ec-7cbc-4e58-8b1c-c1f3de1462d5)
3. Membuat Model untuk memproses data Artikel
   Buat file baru pada direktori app/Models dengan nama ArtikelModel.php
   ![image](https://github.com/user-attachments/assets/d5e447f1-755d-4a25-a83a-e686f103cb32)
4. Buat Controller baru dengan nama Artikel.php pada direktori app/Controllers.
   ![image](https://github.com/user-attachments/assets/d7859c41-a68d-4e09-a79c-654442de8041)
5. Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file baru dengan nama index.php
   ![image](https://github.com/user-attachments/assets/3dbc2eb7-d4af-46cd-8e20-f052d13a3346)
6. buka browser kembali, dengan mengakses url http://localhost:8080/artikel 
   ![image](https://github.com/user-attachments/assets/390ca551-d370-47bf-b625-1d2bcca669ca)
7. Kemudian tambahkan beberapa data pada database agar dapat ditampilkan datanya.
   ![image](https://github.com/user-attachments/assets/b144d6a1-abbb-424a-8763-ce0a4af637d9)
   sehingga menampilkan
   ![image](https://github.com/user-attachments/assets/856c63dc-962a-46a1-88a2-38d10b077344)
8. Tambahkan fungsi baru pada Controller Artikel dan view detail sehingga pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda.
   ![image](https://github.com/user-attachments/assets/5033d25b-7306-4ef8-8ec2-949406dc870d)
9. Membuat Menu Admin dengan cara buat method baru pada Controller Artikel dengan nama admin_index() dan buat view untuk tampilan admin dengan nama admin_index.php serta tambahkan routing untuk menu admin
    ![image](https://github.com/user-attachments/assets/37e9840f-f110-424f-a0e9-1d0aa6ef32bc)
10. Tambah data
    ![image](https://github.com/user-attachments/assets/9c03bb51-791f-4c7d-99b4-6b083c9a1b87)
11. Edit data
    ![image](https://github.com/user-attachments/assets/bb4e84ec-e671-4c53-b5eb-cd45104709d4)
13. Hapus data
    ![image](https://github.com/user-attachments/assets/fbb28377-eddc-4dd1-9fc4-1167cf5b129c)

12. 


    
# manfaat utama dari penggunaan View Layout dalam pengembangan aplikasi
1. untuk membuat template tampilan yang dapat digunakan kembali
2. Layout desain UI tetap seragam di seluruh halaman.
3. Memisahkan Logika dan Tampilan sehingga code lebih bersih dan mudah dibaca



   


