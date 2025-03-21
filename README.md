# My Project
Praktikum 1: PHP Framework (Codeigniter)
Dalam praktikum ini kita akan membuat tampilan seperti berikut
![Screenshot 2025-03-22 002113](https://github.com/user-attachments/assets/92484f33-6886-431b-b0bb-e4578a6aa4d2)

sebelum itu ada beberapa exstensi yang harus diaktifkan, yaitu:
• php-json ekstension untuk bekerja dengan JSON; 
• php-mysqlnd native driver untuk MySQL; 
• php-xml ekstension untuk bekerja dengan XML; 
• php-intl ekstensi untuk membuat aplikasi multibahasa; 
• libcurl (opsional), jika ingin pakai Curl. 

Untuk mengaktifkannya kita setting php.ini pada xampp seperti berikut
![image](https://github.com/user-attachments/assets/cb47a03b-7932-4ba6-a008-24e36916b047)

Lalu download Codeigniter dari website https://codeigniter.com/download kemudian Extrak file zip Codeigniter ke direktori htdocs/lab11_ci dan ubah namanya menjadi ci4

sehingga saat kita mengakses http://localhost:8080/ pada browser menampilkan
![Screenshot 2025-03-21 235111](https://github.com/user-attachments/assets/7b776fc9-39ba-4606-95f4-3ee96a82859c)

Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. 
Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut. 
![Screenshot 2025-03-21 235900](https://github.com/user-attachments/assets/d350fdee-bf8c-4246-b51e-b69bf6fdf047)

Untuk mengaktifkan mode debugging rename file env menjadi .env dan mengubah nilai konfigurasi pada environment variable CI_ENVIRINMENT pada .env menjadi development.
![image](https://github.com/user-attachments/assets/d8d3827e-69f4-43eb-bff3-c11caffe17ff)
Sehingga saat ada kesalahan pada program kita browser akan menampilkan
![Screenshot 2025-03-22 000029](https://github.com/user-attachments/assets/def8f63d-ed58-4707-b2d4-d57d29815e5e)

Langkah-langkah membuatnya
1. Buat route Tambahkan kode berikut di dalam Routes.php 
   $routes->get('/about', 'Page::about'); 
  $routes->get('/contact', 'Page::contact'); 
  $routes->get('/faqs', 'Page::faqs');
Jika berhasil saat ketik php spark routes pada CMD menampilkan:
![Screenshot 2025-03-22 000409](https://github.com/user-attachments/assets/82bf7eeb-4988-42d4-ba21-1bf7f22f3ebc)
2. Buat Controller pada directory Controller
   Buat file page.php kemudian isi kodenya seperti berikut.
   ![image](https://github.com/user-attachments/assets/7318a866-971f-472b-a43d-7884b4bf5058)
  Setelah itu saat kita membuka http://localhost:8080/about akan menampilkan
![Screenshot 2025-03-22 001349](https://github.com/user-attachments/assets/68f154bd-58bd-4cb7-9d18-fcfb1612454c)
3. buat View 
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
