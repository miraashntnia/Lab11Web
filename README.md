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

