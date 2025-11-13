Halo! Saya Danish, seorang *software engineer* dengan spesialisasi *full-stack development* dan minat kuat pada AI, IoT, dan DevOps.  
Saya adalah Juara 3 Lomba Kompetensi Siswa (LKS) Provinsi Jawa Tengah di bidang IT Software Solution.

Saya percaya bahwa "**membangun**" adalah cara belajar terbaik.  
Di bawah ini adalah beberapa studi kasus dari proyek yang pernah saya kerjakan, baik proyek pribadi maupun profesional.

**Kontak:**
- **Email:** danishabyanpratista@gmail.com  
- **LinkedIn:** [linkedin.com/in/danish-abyan-pratista](https://linkedin.com/in/danish-abyan-pratista)
---
## 🚀 Proyek Unggulan (Studi Kasus)
### 1. Management Tamu [Internal Platform]
- **Skala:** Enterprise  
- **Status:** Profesional (Private/NDA)  
- **Perusahaan:** PT Malifax Indonesia  
- **Peran:** Internship Software Developer (dengan tawaran Karyawan Tetap)
- **Tech Stack:** `NodeJS`, `Microservice`, `TimeSeriesDB`, `FileSystem`, `Computer Vision`, `IoT`
#### Ringkasan
Merancang, mengembangkan, dan memelihara sebuah sistem manajemen tamu terintegrasi yang dilengkapi dengan *real-time tracking* tamu dan perangkat (baik tamu maupun staf) tanpa memerlukan aplikasi tambahan, sekaligus menyediakan fitur manajemen jaringan WiFi untuk memastikan konektivitas dan pengawasan yang efisien di seluruh area operasional.
#### Tantangan & Solusi (Tersensor)
* **Tantangan 1: Skalabilitas Data (Velocity & Volume Tinggi)**  
	- **Masalah:** Sistem harus mampu menangani aliran data yang besar dan cepat dari berbagai perangkat secara *real-time*, yang berpotensi menimbulkan *bottleneck* saat proses penyimpanan dan analisis.  
	- **Solusi:** Mengimplementasikan arsitektur *event-driven* berbasis *multi-threaded workers* untuk memproses data secara paralel, serta menggunakan **time-series database** guna mengelola data dengan efisien sesuai urutan waktu. Pendekatan ini memungkinkan sistem tetap responsif dan skalabel meski beban data meningkat secara signifikan.
* **Tantangan 2: Ketersediaan & Keandalan Layanan (High Availability & Reliability)**  
	- **Masalah:** Sistem harus selalu tersedia tanpa gangguan, bahkan saat terjadi kegagalan pada salah satu layanan atau node.  
	- **Solusi:** Menerapkan arsitektur **microservice** dengan dukungan **load balancer** dan **circuit breaker pattern** untuk menjaga stabilitas antar layanan. Selain itu, menerapkan praktik terbaik penulisan kode dan efisiensi algoritma agar setiap layanan ringan, mudah dipelihara, dan tahan terhadap gangguan.
* **Tantangan 3: Optimasi Query & Efisiensi Proses Data**  
	- **Masalah:** Beberapa proses analitik membutuhkan waktu lama karena kompleksitas pengolahan data di sisi aplikasi.  
	- **Solusi:** Memindahkan sebagian besar logika pengolahan data ke **database level** untuk memanfaatkan kemampuan optimasi internal DBMS, disertai *indexing* dan agregasi efisien. Selain itu, menggunakan beberapa *algorithmic tricks* (teknik rahasia optimasi) untuk memangkas waktu eksekusi tanpa mengorbankan akurasi hasil.
> *Catatan: Karena Perjanjian Kerahasiaan (NDA), kode sumber, arsitektur detail, dan nama proyek spesifik tidak dapat dipublikasikan. Detail lebih lanjut dapat didiskusikan saat wawancara.*
### 2. Aplikasi Sistem Absensi Berbasis Wajah (IoT x AI)
- **Status:** Proyek Pribadi (Publik)  
- **Tech Stack:** `FastAPI (Python)`, `PHP`, `YuNet (Model)`, `SFace (Model)`, `ESP32`, `C++`  
- **Repository:** [Link ke GitHub Anda]
#### Ringkasan
Sistem absensi wajah *end-to-end*. Perangkat keras (ESP32) menangkap wajah, mengirimkannya ke *backend* AI (FastAPI) untuk pengenalan, dan hasilnya dicatat di *dashboard* admin (PHP).
#### Arsitektur Konseptual
1. **Perangkat (ESP32):** Menggunakan C++ untuk menangkap gambar saat mendeteksi wajah.  
2. **API Service (FastAPI):** Menerima gambar, lalu menjalankan model AI (YuNet & SFace) untuk mendeteksi dan mengenali wajah.  
3. **Web Dashboard (PHP):** Antarmuka admin untuk mendaftarkan wajah baru, mengelola data pengguna, dan melihat riwayat absensi.
#### Tantangan & Solusi
* **Tantangan 1: Akurasi & Kecepatan Pengenalan Wajah**  
    - **Masalah:** Model *face recognition* standar sering lambat dan tidak akurat dalam kondisi cahaya rendah.  
    - **Solusi:** Menggunakan kombinasi **YuNet** (deteksi wajah cepat) dan **SFace** (pengenalan akurat). Kombinasi ini memberikan keseimbangan terbaik antara kecepatan dan akurasi untuk perangkat IoT.
* **Tantangan 2: Integrasi Multi-Teknologi**  
    - **Masalah:** Proyek ini melibatkan 3 bahasa/platform berbeda (C++, Python, PHP) yang harus berkomunikasi dengan mulus.  
    - **Solusi:** Merancang alur data berbasis API yang jelas. **FastAPI (Python)** berperan sebagai otak AI, sementara **PHP** bertindak sebagai antarmuka admin yang mengonsumsi API tersebut, memisahkan logika AI dari logika bisnis.
### 3. Platform Manajemen Usaha Laundry
- **Status:** Proyek Pribadi (Publik)  
- **Tech Stack:** `NestJS`, `Vite (React)`, `TailwindCSS`, `MaterialUI`, `PostgreSQL`  
- **Repository:** [AbyanCore/Laundry-Webapp](https://github.com/AbyanCore/Laundry_Webapp)
#### Ringkasan
Platform *full-stack* untuk manajemen bisnis laundry. Fiturnya mencakup pelacakan pesanan, manajemen keuangan, analisis performa bisnis, dan dukungan multi-outlet.
#### Tantangan & Solusi
* **Tantangan 1: Arsitektur Backend yang Terstruktur**  
    - **Masalah:** Proyek ini memiliki banyak fitur kompleks (keuangan, inventaris, multi-outlet) yang dapat menjadi “kode spageti” jika tidak dirancang dengan baik.  
    - **Solusi:** Menggunakan **NestJS** sebagai *backend* dengan arsitektur modular (*Module*, *Controller*, *Service*), sehingga kode menjadi terstruktur, bersih, dan mudah di-*maintain*.

* **Tantangan 2: Antarmuka yang Cepat dan Fungsional**  
    - **Masalah:** Admin *dashboard* harus cepat dan responsif meskipun memuat banyak data.  
    - **Solusi:** Menggunakan **Vite + React** untuk *frontend* karena kecepatan *build* dan *hot-reload* yang tinggi. Menggabungkan **TailwindCSS** (untuk *layouting* cepat) dengan **MaterialUI** (untuk komponen kompleks seperti tabel dan *chart*).

* **Tantangan 3: Logika Bisnis yang Rumit**  
    - **Masalah:** Fitur "analisis performa bisnis" memerlukan *query database* kompleks untuk menghitung pendapatan, profit, dan item terlaris.  
    - **Solusi:** Merancang skema **PostgreSQL** yang dinormalisasi dan menggunakan *TypeORM* dari NestJS untuk membangun *query* agregat kompleks. Hasilnya, *dashboard* analitik dapat menampilkan data relevan tanpa membebani aplikasi.
---
## 📁 Proyek Lainnya
-  **RSVP Online (Undangan Pernikahan)**
	- **Stack:** Next.js, TailwindCSS, Directus (CMS), Groq API (Integrasi AI), LM Studio (Local AI)  
	- **Deskripsi:** Platform undangan digital interaktif yang memungkinkan tamu melakukan RSVP secara online, memberikan ucapan selamat, serta melihat galeri foto acara.  
	- **Fitur Unggulan:**
	  - **RSVP otomatis** dengan notifikasi langsung ke pasangan pengantin.  
	  - **Galeri foto** dan **pesan ucapan** yang ditampilkan langsung di halaman undangan.  
	  - **Integrasi AI terbatas** menggunakan Groq API atau Local AI untuk menghasilkan ucapan personal dan rekomendasi balasan.  
- **Website Profil & Portal Divisi ITSC**
	- **Links:** [Website ITSC](https://webitsc.vercel.app/)
	- **Stack:** Next.js, TailwindCSS, PrismaClient, PostgreSQL  
	- **Deskripsi:** Portal resmi Divisi ITSC (Information Technology Study Community) sebagai pusat informasi, administrasi, dan pengelolaan kegiatan organisasi.  
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
