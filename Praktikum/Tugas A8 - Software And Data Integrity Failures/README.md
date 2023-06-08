## Cover

<h3 align="center">
    <b>Praktikum Kemanan Jaringan</b><br>
    A8 - Software And Data Integrity Failures (OWASP 10 Juice Shop)
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

# Laporan

A8 - Software and Data Integrity Failures adalah salah satu kategori kerentanan keamanan yang terkait dengan kegagalan atau kelemahan dalam menjaga integritas perangkat lunak dan data yang digunakan dalam suatu sistem atau aplikasi. Kerentanan ini dapat mengakibatkan manipulasi data, perubahan tidak sah, atau kerusakan pada perangkat lunak atau data yang dapat mempengaruhi kehandalan, keandalan, dan kebenaran sistem. 

1. Kerentanan ini terjadi ketika penyerang berhasil memodifikasi atau memanipulasi data yang ada dalam sistem dengan cara yang tidak sah. Hal ini dapat mengakibatkan kerusakan atau penyimpangan data yang dapat mempengaruhi integritas sistem.

2. Ketika perangkat lunak atau sistem melakukan pembaruan atau pemutakhiran, jika proses ini tidak diamankan dengan baik, penyerang dapat memanfaatkannya untuk memasukkan perangkat lunak berbahaya atau merusak integritas data.

3. Jika sistem tidak melakukan validasi input yang memadai, penyerang dapat memasukkan data yang merusak atau mencurigakan yang dapat menyebabkan kerusakan atau manipulasi pada perangkat lunak atau data.

4. Kerentanan pada komponen perangkat lunak, seperti kerentanan pada perpustakaan atau framework yang digunakan, dapat mengakibatkan kerentanan integritas data atau perangkat lunak yang digunakan dalam sistem.

Untuk mengatasi kerentanan A8 - Software and Data Integrity Failures, penting untuk menerapkan praktik keamanan perangkat lunak yang baik, termasuk melindungi dan mengamankan pembaruan perangkat lunak, melakukan validasi input yang cermat, mengamankan komponen perangkat lunak yang digunakan, memiliki mekanisme pemulihan kesalahan yang andal, serta menerapkan kontrol akses yang memadai pada pemrosesan data sensitif. Selain itu, pengujian keamanan perangkat lunak secara reguler dan pemantauan aktivitas mencurigakan dapat membantu mendeteksi dan mencegah kerentanan integritas perangkat lunak dan data.

Berikut adalah kerentanan yang terdapat pada aplikasi OWASP Juice Shop: <br>

**PERCOBAAN**

1. Buka aplikasi OWASP Juice Shop <br>
   ![Screenshot](images/1.png) <br>
2. Berikan /ftp pada path url aplikasi Juice Shop <br>
   ![Screenshot](images/2.png) <br>
3. Klik package.json.bak <br>
   ![Screenshot](images/3.png) <br>
4. Buka Burpsuite dan masuk ke menu Decoder, masukkan %00 <br>
   ![Screenshot](images/4.png) <br>
5. Lakukan Encode as URL <br>
   ![Screenshot](images/5.jpg)
   <![Screenshot](images/6.png)
6. Copy hasil encode pada URL package.json.bak <br>
   ![Screenshot](images/7.png)
7. Kode dapat diunduh <br>
   ![Screenshot](images/8.png) <br>
   ![Screenshot](images/9.png) <br>
