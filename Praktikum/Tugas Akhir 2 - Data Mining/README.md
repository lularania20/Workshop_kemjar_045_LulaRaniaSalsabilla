## Cover

<h3 align="center">
    <b>Praktikum Kemanan Jaringan</b><br>
   Data Mining Using KNIME
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

<b><h3 align="center"> DATA MINING USING KNIME </h3></b><br>

1.  Bagi File menjadi 5 bagian : init.pcap, init2.pcap, init3.pcap, init4.pcap, init5.pcap <br>
    ![Screenshot](images/1.png)<br>
2.  Kemudian buka file tersebut secara bergantian menggunakan Wireshark. Pada langkah ini kita gunakan file init.pcap <br>
    ![Screenshot](images/2.png)<br>
3.  Untuk proses analisis yang akan dilakukan nantinya, kita akan mengambil data dengan ip versi 4 (ipv4) dan protocol TCP, DNS saja. Untuk proses tersebut dapat dilakukan pada wireshark menggunakan perintah ip.version==4 && tcp || dns pada kolom display filter tepat dibawah toolbar <br>
    ![Screenshot](images/3.png)<br>
4.  Untuk mendapatkan delta time dan delta time dan delta time display, klik Edit – Preferences – Column
    ![Screenshot](images/4.png)<br>
    Hasilnya <br>
    ![Screenshot](images/5.png)<br>
5.  Export file pcap tersebut keformat Comma-separated Value (.csv) dengan cara klik File – Export Packet Dissections – As CSV. Yang perlu diperhatikan yaitu pada Pacet Range, pastikan yang terpilih yaitu Displayed, karena data pada Displayed ini sudah terfilter denga nip version 4 <br>
    ![Screenshot](images/6.png)<br>
    ![Screenshot](images/7.png)<br>
6.  Membuat workflow/project baru. Dengan cara klik File – New – New Knime Workflow – Tulis Nama workflow dan Lokasi workflow tersebut – Klik Finish <br>
    ![Screenshot](images/8.png)<br>
7.  Tambahkan data ke dalam file reader <br>
    ![Screenshot](images/9.png)<br>
8.  Gabungkan kelima data dengan menggunakan concatenate dan data reader seperti gambar di bawah <br>
    ![Screenshot](images/10.png)<br>
9.  Untuk melakukan labeling data normal kita akan menggunakan Node Missing Value. Node ini digunakan untuk mengisi data kosong <br>
    ![Screenshot](images/11.png)<br>
10. Untuk memastikan bahwa kolom label sudah terisi dengan value Malicious atau Normal, dapat menggunakan node Value Counter. Node ini berfungsi untuk menghitung jumlah seluruh value pada kolom terpilih. <br>
    ![Screenshot](images/12.png)<br>
11. Export file ke dalam format .csv dengan menggunakan node CSV Writer <br>
    ![Screenshot](images/13.png)<br>
    Data diletakkan di dalam file hasil.csv <br>
    ![Screenshot](images/14.png)<br>
12. Data pre-processing <br>
    Proses dimana data akan dibersihkan (cleaning) karena biasanya didalam suatu data terdapat nilai-nilai yang tidak sempurna atau bahkan terdapat nilai-nilai yang hilang atau kosong yang nantinya akan dapat mempengaruhi proses kedepannya. Pada proses ini kita membutuhkan Node-node berikut : File Reader, Column Filter, Missing Value. <br>
    ![Screenshot](images/15.png)<br>
13. Proses data transformation, pada proses ini data akan diubah ke format yang sesuai untuk proses data mining. Node yang digunakan pada tahap ini yaitu Normalizer. Berikut konfigurasinya: <br>
    ![Screenshot](images/16.png)<br>
14. Data Mining <br>
    Setelah menyelesaikan tahap data transformation, kita akan menjalankan proses Data Mining, dalam proses ini kita akan menggunakan Metode Klasifikasi Decision Tree dengan teknik Cross Validation. Pada proses ini kita membutuhkan Node-node berikut : X-Partitioner, Decision Tree Learner, Decision Tree Predictor, X-Aggregator Sehingga akan membentuk flow seperti ini <br>
    ![Screenshot](images/17.png)<br>
15. Node Scorer yang didalamnya terdapat perhitungan untuk melihat seberapa baik model ini dengan menggunakan teknik confusion matrix. Berikut konfigurasinya. <br>
    ![Screenshot](images/18.png)<br>
16. Hasil prediksi <br>
    ![Screenshot](images/19.png)<br>
