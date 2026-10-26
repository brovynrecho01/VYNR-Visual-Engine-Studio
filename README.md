# VYNR Visual Engine — SaaS Creative Studio (Portfolio Edition)

![VYNR Visual Engine Banner](https://via.placeholder.com/1200x600/09090b/e5b84b?text=VYNR+Visual+Engine) <!-- Ganti dengan URL banner asli Anda jika ada -->

VYNR Visual Engine adalah aplikasi web inovatif berbasis antarmuka *Non-Linear Editor* (NLE) yang dirancang khusus untuk mempercepat produksi konten bergaya *dark aesthetic* (Reels 9:16 dan Carousel 3:4). Aplikasi ini beroperasi **sepenuhnya di sisi klien (client-side)**, menghadirkan performa rendering MP4 yang cepat tanpa memerlukan infrastruktur *backend* atau server rendering tambahan.

Proyek ini merupakan edisi portofolio yang telah disanitasi, mendemonstrasikan kemampuan pengembangan *front-end* yang kuat, pemrosesan media tingkat lanjut, dan desain UI/UX yang imersif.

## ✨ Fitur Utama

*   **CapCut-Style Multi-Track Timeline (9:16 Reels Mode):**
    *   Antarmuka *timeline* interaktif untuk menyusun *footage* (B-Roll).
    *   Fitur potong (split), tambah, hapus, dan atur durasi klip secara instan.
    *   Pengaturan pergerakan kamera dinamis (Ken Burns effect: *Zoom In, Zoom Out, Pan Up*).
    *   Sistem tipografi multi-skenario (satu teks utama atau teks dinamis per klip) yang terintegrasi dengan zona aman (Safe Zone) Reels.
*   **Carousel Studio (3:4 Mode):**
    *   Editor *slide-by-slide* untuk membuat konten mikro-pembelajaran dan studi kasus.
    *   Kustomisasi latar belakang (*background*) individual atau massal (mendukung pengunggahan gambar lokal).
    *   Kontrol *framing* latar (Zoom dan Focal Y).
*   **100% Client-Side MP4 Video Rendering:**
    *   Menggunakan teknologi mutakhir **WebCodecs API** (`VideoEncoder`) dan `mp4-muxer` untuk menghasilkan file MP4 H.264 asli dengan kecepatan tinggi langsung di peramban.
    *   Sistem *fallback* otomatis menggunakan `MediaRecorder` jika WebCodecs tidak didukung oleh peramban pengguna.
*   **Color Grading & Cinematic Filters:**
    *   Filter visual kustom yang terintegrasi (`bushido_sepia`, `mono_grit`, `bateman_cold`, dll.) untuk mempertahankan estetika merek yang konsisten.
    *   Kontrol opasitas gelap (*darkness slider*) dan efek vinyet (*vignette*) otomatis untuk keterbacaan teks.
    *   Animasi partikel sekitar (*ambient particles*) seperti debu/daun yang jatuh untuk menambah kedalaman visual.
*   **Security & Performance Hardened:**
    *   **DOM-based XSS Protection:** Semua input pengguna (*copywriting*, judul file) disanitasi dengan ketat menggunakan utilitas `escapeHTML`.
    *   **Memory Management:** Manajemen memori yang efisien dengan pembersihan (*revocation*) `ObjectURL` otomatis untuk mencegah kebocoran memori (*memory leaks*) saat mengunggah banyak media.
    *   **Content Security Policy (CSP):** Dilengkapi dengan meta tag CSP dasar untuk lapisan keamanan tambahan.

## 🚀 Cara Menjalankan (Pengembangan Lokal)

Karena aplikasi ini sepenuhnya berbasis sisi klien, Anda dapat menjalankannya dengan mudah tanpa perlu menginstal dependensi (seperti `npm install`).

1.  **Clone repositori:**
    ```bash
    git clone https://github.com/username-anda/VYNR-Visual-Engine-Portfolio.git
    cd VYNR-Visual-Engine-Portfolio
    ```
2.  **Jalankan server lokal sementara:**
    Untuk menghindari masalah kebijakan CORS (Cross-Origin Resource Sharing) yang mungkin muncul saat memuat *script* eksternal dari CDN jika Anda membuka file secara langsung (menggunakan `file://`), sangat disarankan untuk menjalankan server web lokal sederhana.

    Jika Anda memiliki **Python** terinstal, Anda dapat menggunakan:
    ```bash
    # Python 3
    python -m http.server 8000
    ```

    Atau, jika Anda menggunakan **Node.js**, Anda dapat menggunakan utilitas seperti `serve`:
    ```bash
    npx serve .
    ```
3.  **Buka di Peramban:**
    Buka peramban Anda dan kunjungi `http://localhost:8000` (atau port yang digunakan oleh server lokal Anda).

## 🌍 Cara *Deploy* (Penerapan)

Repositori ini siap untuk di-*deploy* ke layanan hosting statis populer hanya dalam hitungan detik.

### Menggunakan Vercel atau Netlify
Cara paling mudah adalah dengan menghubungkan repositori GitHub Anda ke Vercel atau Netlify.
*   **Vercel:** Repositori ini sudah menyertakan file `vercel.json` yang berisi konfigurasi *security headers* (seperti `X-Content-Type-Options: nosniff`, `X-Frame-Options: DENY`). Cukup *import* repositori di dashboard Vercel, dan aplikasi akan langsung tayang.
*   **Netlify:** Anda juga dapat mengimpor repositori ini ke Netlify.

### Menggunakan GitHub Pages
1. Masuk ke pengaturan (Settings) repositori di GitHub.
2. Di sidebar kiri, pilih bagian "Pages".
3. Pada bagian "Build and deployment", pastikan "Source" diatur ke "Deploy from a branch".
4. Di bawah pilihan "Branch", pilih `main` (atau cabang utama Anda) dan biarkan foldernya `/ (root)`.
5. Klik "Save". GitHub Pages akan mulai mem-build situs Anda.

## 🛠️ Teknologi yang Digunakan

*   **HTML5 Canvas API:** Untuk rendering komposisi visual tingkat piksel (video, gambar, teks, dan partikel).
*   **WebCodecs API & mp4-muxer:** Untuk proses enkoding video H.264 (*client-side*).
*   **Vanilla JavaScript (ES6+):** Logika inti aplikasi, manajemen status (*state management*), manipulasi DOM, dan sistem interaktif *timeline*.
*   **Tailwind CSS (via CDN):** Digunakan untuk merancang *User Interface* (UI) yang modern, responsif, dan bernuansa gelap (*dark theme*).

## 📄 Lisensi
[PILIH SALAH SATU ATAU SESUAIKAN: Proyek ini bersifat *Open Source* di bawah lisensi MIT. ATAU: Hak Cipta dilindungi. Proyek ini ditujukan untuk keperluan portofolio.]
