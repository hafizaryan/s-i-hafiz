# Jelajah Nusantara

Aplikasi web satu halaman (single page application) untuk membagikan cerita perjalanan di berbagai daerah di Indonesia, lengkap dengan penanda lokasi pada peta. Aplikasi ini merupakan proyek submission kelas pengembangan web tingkat intermediate di Dicoding, yang mengonsumsi Dicoding Story API.

## Fitur

- Registrasi dan login pengguna, dengan token akses yang disimpan di browser
- Beranda berisi daftar cerita dari pengguna lain setelah login
- Menambah cerita baru melalui halaman tambah cerita
- Rute aplikasi berbasis hash: `#/login`, `#/register`, `#/` (beranda), dan `#/new` (tambah cerita)
- Peta interaktif menggunakan Leaflet untuk menampilkan lokasi cerita
- Notifikasi dan dialog interaktif menggunakan SweetAlert2

## Teknologi

- JavaScript (ES Module) dengan bundler Webpack 5
- Babel melalui babel-loader dan @babel/preset-env
- Leaflet untuk peta
- SweetAlert2 dan tiny-slider
- Prettier untuk konsistensi format kode
- http-server untuk menyajikan hasil build

## Struktur Proyek

```text
s-i-hafiz/
├── src/
│   ├── index.html          # Kerangka halaman utama
│   ├── public/             # Aset publik
│   ├── scripts/            # Kode aplikasi
│   │   ├── config.js       # Konstanta, termasuk BASE_URL API
│   │   ├── data/api.js     # Fungsi pemanggilan Dicoding Story API
│   │   ├── pages/          # Halaman auth, home, dan new
│   │   ├── routes/         # Definisi rute dan url parser
│   │   ├── utils/          # Utilitas, termasuk pemeriksaan autentikasi
│   │   └── templates.js    # Template HTML
│   └── styles/             # Berkas CSS
├── submission-intermediate/
├── webpack.common.js
├── webpack.dev.js
└── webpack.prod.js
```

## Cara Menjalankan

Prasyarat: Node.js dan npm.

```bash
npm install
```

Mode pengembangan (webpack dev server):

```bash
npm run start-dev
```

Build produksi, lalu sajikan folder `dist`:

```bash
npm run build
npm run serve
```

Perintah `serve` menjalankan http-server pada port 3000.

## API

Aplikasi ini menggunakan Dicoding Story API pada `https://story-api.dicoding.dev/v1`. Koneksi internet diperlukan karena data cerita dan autentikasi dikelola sepenuhnya oleh API tersebut.
