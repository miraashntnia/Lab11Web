# Lab11Web
```
                                                 MIRA SHINTANIA
                                                   312010290
                                                    TI.20.B2
```
## PRAKTIKUM 11 : PHP Framework (Codeigniter)

### Persiapan
Sebelum memulai menggunakan Framework Codeigniter, perlu dilakukan konfigurasi pada webserver. Beberapa ekstensi PHP perlu diaktifkan untuk kebutuhan pengembangan Codeigniter 4.
Berikut beberapa ekstensi yang perlu diaktifkan:
+ php-json ekstension untuk bekerja dengan JSON;
+ php-mysqlnd native driver untuk MySQL;
+ php-xml ekstension untuk bekerja dengan XML;
+ php-intl ekstensi untuk membuat aplikasi multibahasa;
+ libcurl (opsional), jika ingin pakai Curl.

Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik Config -> PHP.ini
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/1.png)
Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.

### Instalasi Code Igniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara 
manual.
+ Unduh Codeigniter dari website https://codeigniter.com/download
+ Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.
+ Ubah nama direktory framework-4.x.xx menjadi ci4.
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/2.png)
+ Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/3.png)

### Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt. 
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/4.png)

### Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program.
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/er.jpg)
Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable CI_ENVIRINMENT menjadi development

Sebelum diubah
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/5%20sebelum%20diubah.png)

Sesudah diubah
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/5%20sesudah%20diubah.png)

![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/8.png)
Contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file app/Controller/Home.php hilangkan titik koma pada akhir kode.
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/7%20sebelum.png)
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/7%20sesudah.png)

### Routing dan Controller
Routing merupakan proses yang mengatur arah atau rute dari request untuk menentukan fungsi/bagian mana yang akan memproses request tersebut. Pada framework CI4, 
routing bertujuan untuk menentukan Controller mana yang harus merespon sebuah request. Controller adalah class atau script yang bertanggung jawab merespon sebuah 
request.
Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk meudian oleh router tesebut diarahkan ke Controller. 
Router terletak pada file app/config/Routes.php
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/9.png)
Tambahkan kode berikut di dalam Routes.php
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/9%20sesudah.png)

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut.
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/10.png)

### Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada direktori Controller kemudian isi kodenya seperti berikut.
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/11.png)
Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url http://localhost:lab_ci/ci4/public/about
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/13.png)

### Auto Routing
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai truemenjadi false.
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/14.png)
Tambahkan method baru pada Controller Page seperti berikut
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/15.png)
Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan alamat: http://localhost:lab_ci/ci4/public/tos
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/16.png)

### Membuat View
Selanjutnya dalam membuat view untuk tampilan web agar lebih menarik. Buat file baru dengan nama about.php pada direktori view (app/view/about.php) kemudian isi kodenya seperti berikut.
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/17.png)

Ubah method about pada class Controller Page menjadi seperti berikut:
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/18.png)
Kemudian lakukan refresh pada halaman tersebut.
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/19.png)

### Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css dan javascript terletak pada direktori public. 
Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/20.png)
Kemudian buat folder template pada direktori view kemudian buat file header.php dan footer.php
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/21.png)
File app/view/template/header.php
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/22.png)
File app/view/template/footer.php
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/23.png)
Kemudian ubah file app/view/about.php seperti berikut
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/24.png)

Selanjutnya refresh tampilan pada alamat http://localhost:8080/about
![1](https://github.com/miraashntnia/Lab11Web/blob/master/img_lab11/25.png)

# Lab12Web
```
                                                 MIRA SHINTANIA
                                                   312010290
                                                    TI.20.B2
```
## PRAKTIKUM 12 : PHP Framework Lanjutan (CRUD)

### Persiapan
Untuk memulai membuat aplikasi CRUD sederhana, yang perlu disiapkan adalah database server menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan melalui XAMPP.

### Membuat Database
![1](https://user-images.githubusercontent.com/72985112/174717928-87d2cde9-a1fb-4e06-a564-a3e8165090ee.png)

### Membuat Tabel
![2](https://user-images.githubusercontent.com/72985112/174717993-d95c8dc9-e650-4b03-97a0-0b84a990a864.png)

![3](https://user-images.githubusercontent.com/72985112/174717970-d832536f-3e0b-4aa9-a803-e6cefd753364.png)

### Konfigurasi Koneksi Database
Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server. Konfigurasi dapat dilakukan dengan du acara, yaitu pada file app/config/database.phpatau menggunakan file .env. Pada praktikum ini kita gunakan konfigurasi pada file .env
![4](https://user-images.githubusercontent.com/72985112/174718055-9db908c6-95ed-46e8-8fdb-e31beef63b62.png)

### Membuat Model
Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada direktori app/Models dengan nama ArtikelModel.php
![5](https://user-images.githubusercontent.com/72985112/174718112-1b817a0a-bc4b-4a42-8e82-f58053ae8929.png)

### Membuat Controller
Buat Controller baru dengan nama Artikel.php pada direktori app/Controllers.
![6](https://user-images.githubusercontent.com/72985112/174718148-b2ecb21e-1c68-4929-b87d-dd5b5b949f05.png)

### Membuat View
Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file baru dengan nama index.php. 
![7](https://user-images.githubusercontent.com/72985112/174718173-2e554aa0-6b52-43b8-9585-1d83c1bf31f2.png)
![8](https://user-images.githubusercontent.com/72985112/174718254-bff87af9-c8d0-44f3-8fb1-d09829573378.png)

Selanjutnya buka browser kembali, dengan mengakses url http://localhost:8080/artikel
![9](https://user-images.githubusercontent.com/72985112/177474704-fc8d6113-0a7c-401c-95ab-09acd9fc0b58.png)
Kemudian coba tambahkan beberapa data pada database agar dapat ditampilkan datanya
Refresh kembali browser, sehingga akan ditampilkan hasilnya.
### Membuat Tampilan Detail Artikel
Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda. Tambahkan fungsi baru pada Controller Artikel dengan nama view()
![10](https://user-images.githubusercontent.com/72985112/177474709-f437b9e0-1610-4f03-8a70-175c1bc957d0.png)
![11](https://user-images.githubusercontent.com/72985112/177474715-24d67530-94cb-4c02-8cfa-eb3ef2380d65.png)
![12](https://user-images.githubusercontent.com/72985112/177474720-23dd5991-9191-4833-93cf-da659c044f69.png)
![13](https://user-images.githubusercontent.com/72985112/177474721-9743f005-20d2-4438-8265-2c53c481df55.png)
![14](https://user-images.githubusercontent.com/85112/177474723-e9be07b1-2d4b-4a20-9c5d-429e2dc20184.png)
![16](https://user-images.githubusercontent.com/72985112/177474738-eeb82609-345b-42fa-a63c-db59825b4470.png)
![15](https://user-images.githubusercontent.com/72985112/177474734-3f55e90d-4f7f-4f6f-8f6b-20ac862ca6e2.png)
![17](https://user-images.githubusercontent.com/72985112/177474750-74743b30-171e-4193-9fd2-7c0d9ea13d18.png)
![18](https://user-images.githubusercontent.com/72985112/177474764-7e07bf3b-5188-44e9-a906-6ec1740e7581.png)
![19](https://user-images.githubusercontent.com/72985112/177474768-5f0ca538-a8dc-47d9-97e7-bc990f38599f.png)
![20](https://user-images.githubusercontent.com/72985112/177474771-947a00e9-0fef-44c0-9043-62dd57eee565.png)
![21](https://user-images.githubusercontent.com/72985112/177474784-8e968ac0-a4cc-41d4-92f7-dd42c60f6dbb.png)
![22](https://user-images.githubusercontent.com/72985112/177474789-c7b1e9b1-694b-4288-ba91-2503a1d73015.png)
![23](https://user-images.githubusercontent.com/72985112/177474794-781dd53c-a58a-4bd4-a541-39aa9f70c9ec.png)


# Lab13Web
```
                                                 MIRA SHINTANIA
                                                   312010290
                                                    TI.20.B2
```
## PRAKTIKUM 13 : Framework Lanjutan (Model Login)

1. Membuat Tabel User :

![image](https://user-images.githubusercontent.com/81431392/123540098-20768500-d6f2-11eb-93a6-cb00911e3180.png)

2. Membuat Model User :

![image](https://user-images.githubusercontent.com/81431392/123540179-937ffb80-d6f2-11eb-818b-482d350a93f9.png)

3. Membuat Controller User :

![image](https://user-images.githubusercontent.com/81431392/123540385-87486e00-d6f3-11eb-99f1-458b33b7e5fc.png)

4. Membuat View Login :

![image](https://user-images.githubusercontent.com/81431392/123542712-004dc280-d700-11eb-9d92-211abb9beffd.png)

5. Membuat Database Seeder :
Jalankan pada CLI php spark make:seeder UserSeeder 
Edit file Database/Seeds/UserSeeder.php : 
![image](https://user-images.githubusercontent.com/81431392/123540730-59642900-d6f5-11eb-9a43-32677bb79179.png)
Lalu jalankan lagi CLI php spark db:seed UserSeeder
hasil outputnya : 
![1](https://user-images.githubusercontent.com/72985112/179650388-68a6c28b-c4a4-44d9-9d58-b538ae1ddd09.png)
Ketika isi email,password maka muncul pada halaman portal admin :
![2](https://user-images.githubusercontent.com/72985112/179650397-a6c60cd7-d5f3-461f-bc4b-f543a3977799.png)

6. Menambahkan Auth Filter :
![image](https://user-images.githubusercontent.com/81431392/123542912-ea8ccd00-d700-11eb-926f-8b36650305a9.png) 
 
7. Konfigurasi file app/Config/Filters.php : 
![image](https://user-images.githubusercontent.com/81431392/123542978-55d69f00-d701-11eb-9797-780bcd3f0d63.png) 

8. dan konfigurasi app/Config/Routes.php : 
![image](https://user-images.githubusercontent.com/81431392/123543075-b9f96300-d701-11eb-9117-82d3145dd762.png) 

Hasil outputnya : 
![3](https://user-images.githubusercontent.com/72985112/179650400-b0941c1b-0c73-46d8-9b9d-665847a43bc6.png) 

Fungsi Logout : 
![image](https://user-images.githubusercontent.com/81431392/123544784-b2d65300-d709-11eb-92d7-2ee02d1adcc6.png)

# Lab14Web
```
                                                 MIRA SHINTANIA
                                                   312010290
                                                    TI.20.B2
```
## PRAKTIKUM 14 : Pagination dan Pencarian

1. Membuat pagination, yaitu dengan membuka Kembali Controller Artikel, kemudian modifikasi kode pada method admin_index seperti berikut.
![image](https://user-images.githubusercontent.com/81579730/124349838-7d56cb80-dc1b-11eb-98bb-dd5e5c566fce.png)
![image](https://user-images.githubusercontent.com/81579730/124349867-9cedf400-dc1b-11eb-990c-50aa7658df99.png)
![4](https://user-images.githubusercontent.com/72985112/179650403-d70a5b9f-b9ed-4a96-a577-c4871479d6b7.png)

2. Membuat Pencarian Pencarian data digunakan untuk memfilter data. Saya membuat pencarian data, yaitu dengan membuka kembali Controller Artikel, pada method admin_index ubah kodenya seperti berikut:
![image](https://user-images.githubusercontent.com/81579730/124349838-7d56cb80-dc1b-11eb-98bb-dd5e5c566fce.png)
![image](https://user-images.githubusercontent.com/81579730/124350018-4fbe5200-dc1c-11eb-953c-f9b1ca96388e.png)
![5](https://user-images.githubusercontent.com/72985112/179650405-300d1a87-98ac-4b3d-afec-86156dc0e4d7.png)
![6](https://user-images.githubusercontent.com/72985112/179650406-75bc1f55-a4c4-43b2-8fb9-f9f29b7810e5.png)

3. Menambahkan fungsi unggah gambar pada tambah artikel.Dengan cara membuka kembali Controller Artikel, sesuaikan kode pada method add seperti berikut:
![image](https://user-images.githubusercontent.com/81579730/124350076-afb4f880-dc1c-11eb-83b8-b47058099fc6.png)
![image](https://user-images.githubusercontent.com/81579730/124350097-d3783e80-dc1c-11eb-8be5-846434b6fab4.png)
![7](https://user-images.githubusercontent.com/72985112/179650409-8fe1e1bc-893d-45cb-8f96-876c9e42cf07.png)
![8](https://user-images.githubusercontent.com/72985112/179650410-ccc9feab-e0d0-4ba6-b0ae-7554d91ab1f3.png)
