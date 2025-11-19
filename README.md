# Telegram Invite Clone - Vue.js

Clone halaman invite Telegram yang dibuat menggunakan Vue.js dengan desain modern dan responsif.

##  Fitur

-  Desain modern persis seperti Telegram asli (Dark Theme)
-  Responsive untuk semua ukuran layar
-  Animasi smooth dan interaktif
-  UI/UX yang intuitif
-  Background pattern asli dari Telegram ([pattern.svg](https://telegram.org/img/tgme/pattern.svg?1))
-  Header navigation dengan **logo Telegram 2019** (official) dan tombol download
-  Dark mode dengan card styling yang authentic
-  Logo Telegram dengan gradient klasik (#2AABEE → #229ED9)

##  Cara Menggunakan

### Instalasi Dependencies

```bash
pnpm install
```

### Menjalankan Development Server

```bash
pnpm dev
```

Aplikasi akan berjalan di `http://localhost:3000`

### Build untuk Production

```bash
pnpm build
```

### Preview Build Production

```bash
pnpm preview
```

##  Struktur Project

```
telegram-invite-clone/
├── public/
│   ├── pattern.svg      # Telegram background pattern (official)
│   └── telegram-logo.svg # Telegram logo 2019 (official)
├── src/
│   ├── App.vue          # Komponen utama
│   ├── main.js          # Entry point
│   └── style.css        # Global styles
├── index.html           # HTML template
├── package.json         # Dependencies
├── vite.config.js       # Vite configuration
└── README.md           # Dokumentasi
```

##  Kustomisasi

Anda dapat mengkustomisasi konten channel dengan mengubah nilai di `src/App.vue`:

```javascript
const channelName = ref('Testing')      // Nama channel
const memberCount = ref('1 subscriber') // Jumlah anggota
```

### Mengubah Background Pattern

Pattern background menggunakan SVG asli dari Telegram yang sudah di-download ke folder `public/pattern.svg`.

Jika ingin menggunakan langsung dari URL online:

```css
/* Edit di src/App.vue bagian .background-pattern */
background-image: url('https://telegram.org/img/tgme/pattern.svg?1');
```

### Mengubah Avatar Channel

Edit gradient warna avatar di `src/App.vue`:

```html
<linearGradient id="avatarGradient" x1="0%" y1="0%" x2="0%" y2="100%">
  <stop offset="0%" style="stop-color:#ff8a80;stop-opacity:1" />
  <stop offset="100%" style="stop-color:#ff6e40;stop-opacity:1" />
</linearGradient>
```

### Mengubah Warna Tema

Edit warna background dan card di `src/App.vue`:

```css
.telegram-invite {
  background: #0e0e0e;  /* Background utama */
}

.invite-card {
  background: #2b2b2b;  /* Background card */
}
```

### Mengubah Logo Telegram

Logo Telegram menggunakan versi 2019 (official). Gradient: `#2AABEE` → `#229ED9`.

Jika ingin menggunakan dari file:

```html
<!-- Di header, ganti inline SVG dengan -->
<img src="/telegram-logo.svg" alt="Telegram" width="32" height="32" />
```

Atau customize warna gradient logo di `src/App.vue`:

```html
<linearGradient id="telegramGradient" ...>
  <stop offset="0" style="stop-color:#2AABEE"/>
  <stop offset="1" style="stop-color:#229ED9"/>
</linearGradient>
```

##  Teknologi

- **Vue.js 3** - Progressive JavaScript Framework
- **Vite** - Next Generation Frontend Tooling
- **CSS3** - Modern styling dengan animations

##  Preview Fitur

1. **Join Button** - Tombol utama untuk bergabung ke channel
2. **Preview Channel** - Tombol untuk melihat preview channel
3. **Copy Link** - Copy link invite dengan feedback visual
4. **Hover Effects** - Interaksi smooth pada semua elemen
5. **Floating Animation** - Logo Telegram dengan animasi mengambang

##  Cara Mengintegrasikan dengan Backend

Untuk menggunakan data dinamis dari backend:

1. Install axios atau fetch API
2. Buat service untuk mendapatkan data channel
3. Update nilai di `setup()` function dengan data dari API

Contoh:

```javascript
import { ref, onMounted } from 'vue'

setup() {
  const channelName = ref('')
  
  onMounted(async () => {
    const response = await fetch('/api/channel/info')
    const data = await response.json()
    channelName.value = data.name
  })
}
```

Free to use for personal and commercial projects.--
**Note:** Ini adalah clone untuk tujuan pembelajaran. Desain dan konsep milik Telegram.

🚀 Coba Sekarang:
Upload gambar ke folder public/
Edit baris 84 di App.vue
Refresh browser
Mau saya buatkan contoh dengan placeholder image dulu? 🖼