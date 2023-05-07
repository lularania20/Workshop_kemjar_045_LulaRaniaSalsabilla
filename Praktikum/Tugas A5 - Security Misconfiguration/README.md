## Cover

<h3 align="center">
    <b>Praktikum Kemanan Jaringan</b><br>
    A5 Security Misconfiguration (OWASP 10 Juice Shop)
</h3>
<br>
<p align="center">
  <img src="../../public/logo_pens.png" alt="Logo PENS" width="300">
</p>
<br>
<p align="center">
    Dosen Pembimbing:<br>
    Ferry Astika Saputra, S.T., M.Sc.
</p>
<br>
<p align="center">
    Disusun Oleh:<br>
    Lula Rania Salsabilla (3122640045)
    Fifin Nur Rahmawati (3122640040)
</p>
<br>
<p align="center">
    <b>
        KELAS D4 LJ IT B <br>
        JURUSAN D4 LJ TEKNIK INFORMATIKA <br>
        DEPARTEMEN TEKNIK INFORMATIKA DAN KOMPUTER <br> 
        POLITEKNIK ELEKTRONIKA NEGERI SURABAYA <br>
        2023
    </b>
</p>
<br>


## Laporan 

Security misconfiguration is any error or vulnerability present in the configuration of code that allows attackers access to sensitive data. There are many types of security misconfiguration, but most present the same danger: vulnerability to data breach and attackers gaining unauthorized access to data. [[1](https://www.bing.com/ck/a?!&&p=5e2855493282d18bJmltdHM9MTY4Mjk4NTYwMCZpZ3VpZD0zMmFmYjYwMC0wZDMxLTZkNDgtMzliYy1hNGY1MGM2NzZjNGYmaW5zaWQ9NTQ0Ng&ptn=3&hsh=3&fclid=32afb600-0d31-6d48-39bc-a4f50c676c4f&psq=Security+Misconfiguration+adalah&u=a1aHR0cHM6Ly93d3cuY3Jvd2RzdHJpa2UuY29tL2N5YmVyc2VjdXJpdHktMTAxL3NlY3VyaXR5LW1pc2NvbmZpZ3VyYXRpb24vIzp-OnRleHQ9U2VjdXJpdHklMjBtaXNjb25maWd1cmF0aW9uJTIwaXMlMjBhbnklMjBlcnJvciUyMG9yJTIwdnVsbmVyYWJpbGl0eSUyMHByZXNlbnQsYnJlYWNoJTIwYW5kJTIwYXR0YWNrZXJzJTIwZ2FpbmluZyUyMHVuYXV0aG9yaXplZCUyMGFjY2VzcyUyMHRvJTIwZGF0YS4&ntb=1)].

**Security Misconfiguration** adalah ketika pengembang tidak mengikuti dokumentasi sebuah library, framework atau komponen aplikasi, tidak menerapkan standart konfigurasi yang ada, maka aplikasi tersebut akan memiliki beberapa lobang kecil yang akan bisa dimanfaatkan oleh attacker. Kategori ini sangat lah luas, dibandingkan beberapa kategori sebelumnya, hampir 80% dari kerentanan yang ada beberapa tahun terakhir, terkena kerentanan Security Misconfiguration, ini dikarenakan web aplikasi saat ini sudah banyak teknologi framework yang dapat memberikan support / bantuan dari sisi keamanan. Jika pengembang memanfaatkan design dari framework tersebut maka akan memudahkan pengembang untuk fokus pada aplikasi tanpa harus pusing memikirkan secure coding.

> Banyak hal yang menjadi penyebab sering terjadi akibat dari miskonfigurasi tersebut:
>
> 1.HTTP Only\
> 2.Query Builder\
> 3.X-Frame-options\
> 4.Content-Security Policy\
> 5.CORS\
> 6.Acces Control\
> 7.dll....
>
> List diatas merupakan beberapa hal yang sering sekali di lupakan oleh
> beberapa pengembang.


### A. Error Handling

Memunculkan error, tetapi error yang ditampilkan tidak secara bagus dan konsisten.

1. Menjalankan aplikasi Burp Suite terlebih dahulu

    ![Screenshot](images/2.png)

2. Kemudian buka browser dan pergi ke halaman utama website OWASP Juice Shop

    ![Screenshot](images/3.png)

3. Buka kembali Burp Suite maka akan muncul request baru yaitu /rest/product/search

    ![Screenshot](images/4.png)

4. Masukkan payload /rest/product/search tadi ke repeater lalu ubah enpointnya menjadi text random lalu klik tombol send

    ![Screenshot](images/5.png)
     ![Screenshot](images/6.png)

    Analisis
    Terdapat response error 500 atau internal server error yang disini terlihat terdapat error message yang begitu panjangnya dan tidak tertata


### B. Deprecated Interface

Menggunakan antarmuka B2B usang yang tidak dimatikan dengan benar.

1. Pada halaman utama, klik tombol menu di pojok kiri atas untuk memunculkan sidebar. Setelah itu klik complaint

    ![Screenshot](images/7.png)

2. Setelah sudah masuk ke halaman complaint, isikan form yang ada, dan masukkan file dengan format xml

    ![Screenshot](images/8.png)

3. Setelah itu akan muncul challange Deprecated Interface berhasil di selesaikan seperti ini

    ![Screenshot](images/9.png)

4. Jika kita lihat di proxy history pada burp suite, akan muncul error panjang seperti ini

    ![Screenshot](images/10.png)

