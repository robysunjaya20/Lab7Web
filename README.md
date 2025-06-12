# 💻 Praktikum PHP Framework (CodeIgniter 4)

Repositori ini berisi panduan praktikum untuk memahami dan menerapkan framework **CodeIgniter 4**, mulai dari pengenalan konsep dasar hingga membangun aplikasi sederhana dengan fitur **CRUD**.

---

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
