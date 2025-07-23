# Prosedur Kalibrasi Flow Meter Gas Menggunakan Master Meter

Dokumen ini adalah panduan standar untuk melakukan pekerjaan "Kalibrasi Flow Meter" di fasilitas kalibrasi, berdasarkan proses yang diilustrasikan.

---

## 🎯 TUJUAN

Prosedur ini dibuat sebagai panduan teknis bagi para teknisi dan insinyur dalam melaksanakan kalibrasi pada flow meter gas. [cite_start]Tujuannya adalah untuk memverifikasi dan memastikan **akurasi**, **reliabilitas**, dan **kelayakan** operasi instrumen sesuai dengan standar acuan sebelum digunakan kembali di lapangan, terutama untuk flow meter yang sertifikat kalibrasinya telah habis setelah satu tahun beroperasi.

<img width="912" height="419" alt="image" src="https://github.com/user-attachments/assets/f401d4bb-7cc9-49dc-8680-777d6efd1eda" />

---

## 📚 REFERENSI

Prosedur kalibrasi ini mengacu pada metode perbandingan langsung, di mana unit yang diuji (*specimen*) dibandingkan dengan alat standar berupa **Master Flow Meter** yang memiliki sertifikat kalibrasi yang valid dan tertelusur. Seluruh proses dikontrol dan datanya dicatat melalui sistem **SCADA**.

<img width="962" height="413" alt="image" src="https://github.com/user-attachments/assets/103f691a-809c-4408-b30a-3af8c05a1427" />

---

## 📏 SATUAN PENGUKURAN

Berikut adalah satuan pengukuran standar yang digunakan dalam prosedur ini berdasarkan data dari sistem kontrol dan laporan:

| Parameter | Satuan | Simbol/Singkatan |
| :--- | :--- | :--- |
| Aliran (Flow) | meter kubik per jam | m³/h |
| Volume | meter kubik | m³ |
| Tekanan | millibar | mBar |
| Temperatur | derajat Celcius | degC |
| Kelembaban | Persentase | % |

---

## 🗺️ LINGKUP PEKERJAAN

Lingkup pekerjaan utama adalah melakukan pengecekan dan pengujian fungsi (kalibrasi) pada peralatan **Flow Meter Gas**. Proses ini mencakup pemasangan, pengujian pada berbagai laju alir, pencatatan data, hingga penerbitan laporan hasil kalibrasi.

---

## 🛠️ PEKERJAAN PERSIAPAN

Persiapan yang matang adalah kunci keberhasilan kalibrasi. Pastikan semua peralatan kerja dan perlengkapan keselamatan telah disiapkan sebelum memulai aktivitas.

### Peralatan Kerja
Peralatan berikut wajib disiapkan dan dipastikan dalam kondisi prima:
* **Alat Kalibrasi Utama (Calibration Rig)**, yang terdiri dari:
    * Beberapa **Master Flow Meter** dengan rentang ukur berbeda (contoh: MG100, MG400, MG2500).
    * **Revolver** untuk penyesuaian koneksi pipa sesuai ukuran flow meter yang diuji.
    * **Blower** sebagai penggerak aliran udara.
    * Sensor tekanan (PT), temperatur (TT), dan tekanan diferensial (DPT) yang terkalibrasi.
* **Sistem Kontrol SCADA/HMI** untuk mengoperasikan proses kalibrasi dan mencatat data.
* **Alat Pelindung Diri (APD)** standar.

### ⚠️ Peralatan Keselamatan (APD)
Standar minimum Alat Pelindung Diri (APD) yang wajib digunakan di area kerja:
* **Safety Helmet** (Helm Keselamatan)
* **Safety Glasses** (Kacamata Keselamatan)
* **Safety Shoes** (Sepatu Keselamatan)
* **Gloves** (Sarung Tangan)

---

## ⚙️ TAHAPAN PROSEDUR PEKERJAAN

Prosedur ini mencakup pemasangan, pengujian kebocoran, pengujian kalibrasi multi-titik, dan pelaporan.

<img width="406" height="382" alt="image" src="https://github.com/user-attachments/assets/20e864df-a45e-4410-90ce-0976e576fb9f" />

### 1. Persiapan dan Pemasangan
1.  **Identifikasi Unit**: Siapkan flow meter yang akan dikalibrasi (selanjutnya disebut *specimen*).
2.  **Pemasangan Fisik**: Pasang *specimen* pada dudukan di alat kalibrasi. Pastikan arah aliran sudah benar.
3.  **Koneksi Pipa**: Atur posisi "Revolver" untuk menyambungkan pipa dari Master Meter ke *specimen* sesuai dengan ukuran flensa. Pastikan semua sambungan terpasang kencang.
4.  **Input Data**: Masuk ke sistem kontrol SCADA. Masukkan data *specimen* seperti nomor seri, tipe, dan pabrikan pada halaman "Kalibration Data".
5.  **Input Kondisi Ruangan**: Masukkan data kondisi ruangan kalibrasi (Suhu, Kelembaban, Tekanan Atmosfer) pada HMI.

<img width="967" height="501" alt="image" src="https://github.com/user-attachments/assets/b17050f4-47e9-43ea-aa19-a1cc2826dc1f" />

### 2. Uji Kebocoran (Leak Test)
1.  **Mulai Leak Test**: Dari menu utama HMI, pilih dan jalankan fungsi "Leak Test".
2.  **Observasi**: Sistem akan memberikan tekanan pada jalur perpipaan. Pantau pembacaan tekanan pada HMI untuk memastikan tidak ada penurunan tekanan yang menandakan kebocoran.
3.  **Konfirmasi**: Jika tidak ada kebocoran, lanjutkan ke tahap berikutnya. Jika ada, perbaiki sambungan dan ulangi tes.

<img width="979" height="451" alt="image" src="https://github.com/user-attachments/assets/9a7ab8be-875a-49df-9c81-c1b6ece29fe8" />

### 3. Prosedur Uji Kalibrasi
1.  **Pilih Master Meter**: Pada sistem SCADA, pilih jalur Master Meter yang akan digunakan sebagai referensi (misalnya Master G400 untuk laju alir menengah).
2.  **Mulai Pengujian**: Jalankan sekuens kalibrasi dari HMI. Operator dapat mengatur laju alir melalui "Blower Control".
3.  **Pengujian Multi-Titik**: Proses pengujian dilakukan pada beberapa titik laju alir yang berbeda (contoh: 280 m³/h, 640 m³/h, dan 1600 m³/h) untuk menguji linearitas *specimen*.
4.  **Akuisisi Data**: Selama pengujian, blower akan menarik udara melalui Master Meter dan *specimen* secara seri. Sistem SCADA akan secara otomatis mencatat dan membandingkan:
    * **Volume Total** yang diukur oleh *specimen* (W) dan Master Meter (M).
    * **Temperatur** pada *specimen* (Tw) dan Master Meter (Tm).
    * **Tekanan** pada *specimen* (Pw) dan Master Meter (Pm).
5.  **Observasi Real-time**: Pantau semua parameter yang ditampilkan pada HMI/SCADA (layar *System Diagram* atau *Overview*) untuk memastikan proses berjalan stabil.

   <img width="1029" height="516" alt="image" src="https://github.com/user-attachments/assets/cdd4b157-5dd0-4f13-bee2-e7e0a659f537" />

### 4. Analisis Hasil dan Pelaporan
1.  **Kalkulasi Error**: Setelah pengujian di setiap titik selesai, sistem secara otomatis menghitung "Kesalahan Penunjukan" atau deviasi antara *specimen* dan master.
2.  **Verifikasi Hasil**: Periksa tabel hasil pada layar "Kalibration Data" untuk melihat ringkasan performa *specimen* di setiap titik uji.
3.  **Generate Laporan**: Setelah semua titik selesai diuji, gunakan fungsi "Report" pada sistem untuk menghasilkan laporan akhir kalibrasi.
4.  **Evaluasi Laporan**: Laporan hasil kalibrasi akan menampilkan perbandingan detail, hasil kalkulasi (termasuk koreksi suhu dan tekanan), dan nilai akhir **Akurasi Rata-Rata**. Hasil ini menentukan apakah *specimen* **LULUS** atau **GAGAL** kalibrasi.
6.  **Selesai**: Jika lulus, sertifikat baru dapat diterbitkan. Lepaskan *specimen* dari alat kalibrasi.

   <img width="933" height="375" alt="image" src="https://github.com/user-attachments/assets/2fec667d-16f6-4151-8d5e-fa6281039702" />
   <img width="1036" height="335" alt="image" src="https://github.com/user-attachments/assets/7e4beb9e-eaa4-4435-84b1-ca2782b3bf41" />

   MIT License

Copyright (c) [2025] [tfits18]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

