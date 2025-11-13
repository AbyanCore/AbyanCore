Halo! Saya Danish, seorang *software engineer* dengan spesialisasi *full-stack development* dan minat kuat pada AI, IoT, dan DevOps. [cite_start]Saya adalah Juara 3 Lomba Kompetensi Siswa (LKS) Provinsi Jawa Tengah di bidang IT Software Solution[cite: 5].

Saya percaya pada "**membangun**" sebagai cara belajar terbaik. Di bawah ini adalah beberapa studi kasus dari proyek yang pernah saya kerjakan, baik proyek pribadi maupun profesional.

**Kontak:**
* [cite_start]**Email:** danishabyanpratista@gmail.com [cite: 2]
* [cite_start]**LinkedIn:** linkedin.com/in/danish-abyan-pratista [cite: 2]
---
## 🚀 Proyek Unggulan (Studi Kasus)
### 1. Management Tamu [Internal Platform] 
- **Skala**: Enterprise
* **Status:** Profesional (Private/NDA)
* **Perusahaan:** PT Malifax Indonesia
* **Peran:** Internship Software Developer (dengan tawaran Karyawan Tetap)
* **Tech Stack:** `NodeJS, Microservice, TimeSeriesDB, FileSystem, Computer Vision, IoT`
#### Ringkasan
Merancang, mengembangkan, dan memelihara sebuah sistem manajemen tamu terintegrasi yang dilengkapi dengan _real-time tracking_ tamu dan perangkat (baik tamu maupun staf) tanpa memerlukan aplikasi tambahan, sekaligus menyediakan fitur manajemen jaringan WiFi untuk memastikan konektivitas dan pengawasan yang efisien di seluruh area operasional.
#### Tantangan & Solusi (Tersensor)
* **Tantangan 1: Skalabilitas Data (Velocity & Volume Tinggi)**
	- **Masalah:** Sistem harus mampu menangani aliran data yang besar dan cepat dari berbagai perangkat secara _real-time_, yang berpotensi menimbulkan _bottleneck_ saat proses penyimpanan dan analisis.
	- **Solusi:** Saya mengimplementasikan arsitektur _event-driven_ berbasis _multi-threaded workers_ untuk memproses data secara paralel, serta menggunakan **time-series database** guna mengelola data dengan efisien sesuai urutan waktu. Pendekatan ini memungkinkan sistem tetap responsif dan skalabel meski beban data meningkat secara signifikan.
- **Tantangan 2: Ketersediaan & Keandalan Layanan (High Availability & Reliability)**
	- **Masalah:** Sistem harus selalu tersedia tanpa gangguan, bahkan saat terjadi kegagalan pada salah satu layanan atau node.
	- **Solusi:** Saya menerapkan arsitektur **microservice** dengan dukungan **load balancer** dan **circuit breaker pattern** untuk menjaga stabilitas antar layanan. Selain itu, saya menerapkan praktik terbaik penulisan kode dan efisiensi algoritma untuk memastikan setiap layanan ringan, mudah dipelihara, dan tahan terhadap gangguan.
- **Tantangan 3: Optimasi Query & Efisiensi Proses Data**
	- **Masalah:** Beberapa proses analitik membutuhkan waktu lama karena kompleksitas pengolahan data pada sisi aplikasi.   
	- **Solusi:** Saya memindahkan sebagian besar logika pengolahan data ke sisi **database level** untuk memanfaatkan kemampuan optimasi internal DBMS, disertai _indexing_ dan agregasi efisien. Selain itu, saya menggunakan beberapa _algorithmic tricks_ (teknik rahasia optimasi) untuk memangkas waktu eksekusi secara signifikan tanpa mengorbankan akurasi hasil.
---
> *Catatan: Karena Perjanjian Kerahasiaan (NDA), kode sumber, arsitektur detail, dan nama proyek spesifik tidak dapat dipublikasikan. Detail lebih lanjut dapat didiskusikan saat wawancara.*
---
### 2. Aplikasi Sistem Absensi Berbasis Wajah (IoT x AI)
* **Status:** Proyek Pribadi (Publik)
* [cite_start]**Tech Stack:** `FastAPI (Python)`, `PHP`, `YuNet (Model)`, `SFace (Model)`, `ESP32`, `C++` [cite: 40]
* **Repository:** `[Link ke GitHub Anda]`
#### Ringkasan
[cite_start]Sistem absensi wajah *end-to-end*[cite: 37]. [cite_start]Perangkat keras (ESP32) menangkap wajah, mengirimkannya ke *backend* AI (FastAPI) untuk pengenalan, dan hasilnya dicatat di *dashboard* admin (PHP) [cite: 38-40].
#### Arsitektur Konseptual
1.  **Perangkat (ESP32):** Menggunakan C++ untuk menangkap gambar saat mendeteksi wajah.
2.  [cite_start]**API Service (FastAPI):** Menerima gambar, lalu menjalankan model AI (YuNet & SFace) [cite: 40] untuk mendeteksi dan mengenali wajah.
3.  [cite_start]**Web Dashboard (PHP):** Antarmuka admin untuk mendaftarkan wajah baru, mengelola data pengguna, dan melihat riwayat absensi[cite: 38].
#### Tantangan & Solusi
* **Tantangan 1: Akurasi & Kecepatan Pengenalan Wajah**
    * **Masalah:** Model *face recognition* standar seringkali lambat dan tidak akurat dalam kondisi cahaya rendah.
    * [cite_start]**Solusi:** Saya melakukan riset dan memilih **YuNet** (untuk deteksi wajah cepat) dan **SFace** (untuk pengenalan akurat)[cite: 40]. Kombinasi ini memberikan keseimbangan terbaik antara kecepatan dan akurasi untuk perangkat IoT.
* **Tantangan 2: Integrasi Multi-Teknologi**
    * [cite_start]**Masalah:** Proyek ini melibatkan 3 bahasa/platform berbeda (C++, Python, PHP) [cite: 40] yang harus berkomunikasi dengan mulus.
    * **Solusi:** Merancang alur data berbasis API yang jelas. [cite_start]**FastAPI (Python)** [cite: 40] [cite_start]bertindak sebagai "otak" AI murni, sementara **PHP** [cite: 40] bertindak sebagai "wajah" (antarmuka admin) yang mengkonsumsi API tersebut. Ini memisahkan logika AI dari logika bisnis.
---
### 3. Platform Manajemen Usaha Laundri
* **Status:** Proyek Pribadi (Publik)
* [cite_start]**Tech Stack:** `NestJS`, `Vite (React)`, `TailwindCSS`, `MaterialUI`, `PostgreSQL` [cite: 36]
* [cite_start]**Repository:** `AbyanCore/Laundry-Webapp` [cite: 34]
#### Ringkasan
[cite_start]Platform *full-stack* untuk manajemen bisnis laundry[cite: 34]. [cite_start]Fiturnya mencakup pelacakan pesanan, manajemen keuangan, analisis performa bisnis, dan dukungan multi-outlet[cite: 35].
#### Tantangan & Solusi
* **Tantangan 1: Arsitektur Backend yang Terstruktur**
    * [cite_start]**Masalah:** Proyek ini memiliki banyak fitur kompleks (keuangan, inventaris, multi-outlet) [cite: 35] yang bisa menjadi "kode spageti" jika tidak dirancang dengan baik.
    * [cite_start]**Solusi:** Saya memilih **NestJS** [cite: 36] untuk *backend*. Arsitekturnya yang berbasis *Module*, *Controller*, dan *Service* (mirip Angular) "memaksa" saya untuk menulis kode yang terstruktur, bersih, dan mudah di-*maintain*.

* **Tantangan 2: Antarmuka yang Cepat dan Fungsional**
    * **Masalah:** Admin *dashboard* harus cepat dan responsif, meskipun memuat banyak data.
    * [cite_start]**Solusi:** Menggunakan **Vite + React** [cite: 36] untuk *frontend* karena kecepatan *build* dan *hot-reload* yang instan. [cite_start]Saya menggabungkan **TailwindCSS** (untuk *layouting* cepat) dengan **MaterialUI** (untuk komponen data yang kompleks seperti tabel dan *chart*)[cite: 36].

* **Tantangan 3: Logika Bisnis yang Rumit**
    * [cite_start]**Masalah:** Fitur "analisis performa bisnis" [cite: 35] memerlukan *query database* yang rumit untuk menghitung pendapatan, profit, dan item terlaris.
    * [cite_start]**Solusi:** Merancang skema **PostgreSQL** [cite: 36] yang dinormalisasi dan menggunakan *TypeORM* dari NestJS untuk membuat *query* agregat yang kompleks. Ini memungkinkan *dashboard* analitik menampilkan data yang relevan tanpa memberatkan aplikasi.
---
## Proyek Lainnya
- **RSVP Online (Undangan Pernikahan)**
	- **Stack:** Next.js, TailwindCSS, Directus (CMS), Groq API (Integrasi AI), LM Studio (Local AI)
	- **Deskripsi:** Platform undangan digital interaktif yang memungkinkan tamu untuk melakukan RSVP secara online, memberikan ucapan selamat, serta melihat galeri foto acara.  
	- **Fitur Unggulan:**
	  - **RSVP otomatis** dengan notifikasi langsung kepada pasangan pengantin.  
	  - **Galeri foto** dan **pesan ucapan** yang ditampilkan langsung di halaman undangan.  
	  - **Integrasi AI terbatas** menggunakan Groq API / Local AI untuk menghasilkan ucapan personal dan rekomendasi balasan.  
- **Website Profil & Portal Divisi ITSC**
	- **Stack:** Next.js, TailwindCSS, PrismaClient, PostgreSQL  
	- **Deskripsi:** Portal resmi untuk Divisi ITSC (Information Technology Study Community) yang berfungsi sebagai pusat informasi, administrasi, dan pengelolaan kegiatan organisasi.  
	- **Fitur Unggulan:**
	  - **E-Absensi anggota** dengan integrasi basis data terpusat.  
	  - **E-Kurikulum digital** untuk pengelolaan materi pembelajaran dan dokumentasi kegiatan.  
	  - **Dashboard admin** untuk manajemen divisi, event, dan publikasi konten.  
- **Sistem Tiket** [Internal Platform]
	- **Status:** Profesional (Private/NDA)  
	- **Deskripsi:** Sistem internal untuk pengelolaan tiket dukungan (*support ticket*) antara pengguna dan tim IT dengan komunikasi dua arah yang efisien.  
	- **Fitur Unggulan:**
	  - **Manajemen Tiket Terpusat** admin dapat membuat, menugaskan, dan melacak tiket dari dashboard web.  
	  - **Pelaporan & Notifikasi Realtime** pengguna melaporkan masalah melalui aplikasi Android dengan pembaruan status instan.  
	  - **Cross-Platform Integration** integrasi penuh antara web (admin panel) dan Android (pengguna) untuk sinkronisasi data tiket secara real-time.  
	  - **Riwayat & Analitik Tiket** menyediakan log dan laporan performa penanganan tiket untuk analisis internal.  
