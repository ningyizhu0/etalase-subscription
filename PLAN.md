# Plan: Etalase Langganan Dennis Shop

## Ringkasan

Satu halaman katalog statis untuk Dennis Shop. Isi hanya dua produk: Spotify dan iCloud. Tanpa form, tanpa backend, tanpa dashboard. CTA langsung ke WhatsApp.

Halaman dibuat dengan HTML dan CSS murni. Tidak ada framework, tidak ada build step, dan tidak ada dependensi JavaScript.

## Data Produk

| Produk | Paket | Durasi | Harga |
|---|---|---|---|
| Spotify | Premium Family | 1 bulan | Rp17.500 |
| iCloud | iCloud+ 2 TB | 1 bulan | Rp34.000 |

Brand: **Dennis Shop**

Kontak: **0818143210**

Link WhatsApp: `https://wa.me/62818143210`

> **Dikonfirmasi:** nomor `0818143210` memang 10 digit, langsung dari pemilik. Link `62818143210` dipakai seperti adanya.

## Arah Visual

`Reading this as: katalog langganan digital untuk pembeli Indonesia, bahasa visual editorial price-sheet, dial ENERGY 2 / RHYTHM 2 / MOTION 1.`

Alasan dial:

- **ENERGY 2:** karakter kuat dari tipografi dan harga besar, tanpa gradient atau glow.
- **RHYTHM 2:** intro asimetris, dua baris harga, lalu catatan. Tidak seragam.
- **MOTION 1:** hanya hover, focus, dan transisi warna. Tidak ada animasi scroll.

Konsep: halaman terasa seperti lembar harga cetak, bukan landing page SaaS. Katalog menjadi hero. Tidak ada section katalog terpisah yang mengulang isi.

## Struktur Halaman

```text
[wordmark]                    Harga   Cara pesan   WhatsApp

Spotify dan iCloud,
harga jelas.
Dua paket bulanan. Pilih paket, lalu chat WhatsApp.

01  Spotify Premium Family     1 bulan      Rp17.500   Tanya paket
02  iCloud+ 2 TB               1 bulan      Rp34.000   Tanya paket

Cara pesan: pilih paket, chat WhatsApp, sebutkan paket dan durasi.

[footer: brand, WhatsApp, tahun, catatan merek]
```

### 1. Header

- Wordmark `Dennis Shop` di kiri.
- Nav di kanan: `Harga`, `Cara pesan`, `WhatsApp`.
- `Harga` menuju `#harga`.
- `Cara pesan` menuju `#cara-pesan`.
- `WhatsApp` menuju link eksternal.
- Di layar kecil, nav turun ke baris kedua. Tidak memakai hamburger.

### 2. Intro

- H1: `Spotify dan iCloud, harga jelas.`
- Subline: `Dua paket bulanan dari Dennis Shop. Pilih paket, lalu chat WhatsApp.`
- Tanpa badge di atas headline.
- Tanpa statistik, testimoni, atau logo klien.

### 3. Price Board `#harga`

Dua baris harga, bukan dua kartu.

- Nomor urut `01` dan `02`.
- Nama produk memakai Instrument Serif.
- Nama paket dan durasi memakai Bricolage Grotesque.
- Harga memakai Bricolage Grotesque dengan `font-variant-numeric: tabular-nums`.
- Garis titik-titik menghubungkan nama paket dan harga. Ini motif identitas halaman.
- CTA `Tanya paket` di setiap baris.
- Baris dipisahkan garis 1px, bukan shadow atau kartu.

### 4. Cara Pesan `#cara-pesan`

Satu blok pendek berisi dua langkah nyata:

1. Pilih paket.
2. Chat WhatsApp dan sebutkan paket serta durasi.

Bukan tiga kartu ikon. Bukan section "How It Works" template.

### 5. Footer

Satu baris:

- `© 2026 Dennis Shop.`
- Link WhatsApp.
- `Spotify dan iCloud adalah merek dagang pemiliknya.`

Tanpa empat kolom template. Tanpa link ke halaman yang tidak ada.

## Sistem Visual

### Palette

| Elemen | Nilai |
|---|---|
| Latar | Warm paper `#F4EFE5` |
| Teks | Ink `#191713` |
| Teks sekunder | Muted `#5E574C` |
| Aksen | Burnt orange `#B83B1D` |

Kontras:

- Ink di paper: 15.62:1
- Muted di paper: 6.23:1
- Accent di paper: 4.98:1

Semua teks memenuhi WCAG AA. Aksen dipakai hanya untuk link, hover, dan focus ring. Bukan untuk seluruh halaman.

### Tipografi

- **Heading:** Instrument Serif, 400 dan italic.
- **Body, nav, label, harga:** Bricolage Grotesque, variable.
- **Fallback:** `Georgia, serif` dan `system-ui, sans-serif`.

Alasan:

- Instrument Serif memberi kontras editorial dan membuat harga terasa seperti lembar katalog cetak. Bukan font default AI.
- Bricolage Grotesque menjaga teks UI tetap hangat dan mudah dibaca. Angka memakai `tabular-nums` agar harga rapi.

Skala:

- H1: `clamp(3rem, 8vw, 7rem)`, line-height `0.95`, letter-spacing `-0.02em`.
- Nama produk: `clamp(2rem, 5vw, 4rem)`.
- Harga: `clamp(2rem, 4vw, 3.5rem)`, weight 600.
- Body: 16 sampai 18px, line-height 1.6.
- Nav: 14px, weight 500.

### Layout

- Max width: `1120px`.
- Gutter: `clamp(20px, 5vw, 64px)`.
- Intro: grid 8 kolom untuk H1, 4 kolom untuk subline di desktop.
- Baris harga: `grid-template-columns: 64px minmax(0, 1fr) auto auto`.
- Di bawah 720px, baris harga bertumpuk. Harga dan CTA pindah ke bawah.
- Spasi section tidak seragam. Intro lebih lega, price board lebih rapat.
- Tanpa `100vh` section.
- Tanpa horizontal scroll.

### Bentuk dan Gerak

- Radius: 4px sampai 6px. Bukan pill.
- Shadow: tidak ada.
- Gradient: tidak ada.
- Glassmorphism: tidak ada.
- Glow: tidak ada.
- Motion: hover, focus, dan transisi warna 150ms.
- Hormati `prefers-reduced-motion`.

## Perilaku dan Teknis

### File

```text
index.html
styles.css
DESIGN.md
PLAN.md
```

`app.js` tidak diperlukan. Semua nav, anchor, dan link WhatsApp bekerja tanpa JavaScript.

### Font

Muat dari Google Fonts:

- Bricolage Grotesque variable.
- Instrument Serif 400 dan italic.

Gunakan `preconnect` dan `display=swap`.

### Link WhatsApp

Spotify:

```text
https://wa.me/62818143210?text=Halo%20Dennis%20Shop%2C%20saya%20mau%20Spotify%20Premium%20Family%201%20bulan%20%28Rp17.500%29.
```

iCloud:

```text
https://wa.me/62818143210?text=Halo%20Dennis%20Shop%2C%20saya%20mau%20iCloud%2B%202%20TB%201%20bulan%20%28Rp34.000%29.
```

Semua link memakai `target="_blank"` dan `rel="noopener noreferrer"`.

### Aksesibilitas

- Skip link ke konten utama.
- Landmark semantik: `header`, `main`, `section`, `footer`.
- Satu H1.
- Focus ring 2px dengan offset 2px.
- Tap target minimal 44px.
- Harga tidak hanya dibedakan lewat warna.
- Navigasi bisa dipakai dengan Tab, Enter, dan Shift+Tab.
- Teks bisa di-zoom tanpa merusak layout.

### SEO

- Title: `Spotify Premium Family & iCloud+ 2 TB | Dennis Shop`.
- Meta description: `Harga Spotify Premium Family Rp17.500 dan iCloud+ 2 TB Rp34.000 per bulan di Dennis Shop.`
- Open Graph dasar tanpa gambar, kecuali Anda minta gambar OG.
- Tidak ada klaim palsu, statistik, atau testimoni.

### Tema

Light theme permanen. Alasannya konsep kertas harga dan struk. Bukan dark mode default tanpa alasan. Tidak ada toggle tema.

## Anti-Slop Checklist

- Tidak ada statistik, testimoni, atau FAQ karangan.
- Tidak ada pricing tiga kolom, badge "Most Popular", bento grid, atau kartu fitur identik.
- Tidak ada gradient, glassmorphism, glow, shadow besar, atau ikon Lucide.
- Tidak ada nav mati. Semua link menuju section atau WhatsApp.
- Tidak ada CTA generik seperti "Get Started". CTA: `Tanya paket` dan `Chat WhatsApp`.
- Tidak ada em dash di copy.
- Tidak ada logo atau avatar yang dibuat tanpa persetujuan. Logo produk memakai teks saja.
- Tidak ada file patching lewat script.
- Palet: 2 warna netral inti, 1 aksen. Warna brand Spotify dan iCloud tidak dipakai sebagai warna halaman.
- Setiap keputusan visual punya alasan tertulis di `DESIGN.md`.

## Di Luar Scope

- Form pemesanan.
- Backend, database, atau dashboard admin.
- Payment gateway.
- Dark mode.
- FAQ, testimoni, dan section "Trusted By".
- Produk selain Spotify dan iCloud.
- Logo produk berupa file gambar.

## Langkah Implementasi

1. Konfirmasi nomor WhatsApp lengkap.
2. Tulis `DESIGN.md`: palette, font, dial, dan alasan tiap keputusan.
3. Buat `index.html` dan `styles.css`.
4. Rapikan responsif untuk 360px, 390px, 768px, 1024px, dan 1440px.
5. Cek keyboard: Tab, Enter, focus ring, skip link.
6. Cek kontras dan overflow horizontal.
7. Jalankan halaman dan klik semua link:
   - `Harga` menuju price board.
   - `Cara pesan` menuju blok cara pesan.
   - `WhatsApp` membuka chat dengan pesan yang benar.
   - `Tanya paket` Spotify membuka pesan Spotify.
   - `Tanya paket` iCloud membuka pesan iCloud.
8. Laporkan Delivery Gate: Hard Gate, Purpose-Gate, Liveliness, Craftsmanship.

## Kriteria Selesai

- Hanya dua produk yang tampil.
- Harga dan durasi sesuai data.
- Semua link bekerja.
- Tidak ada horizontal scroll di semua breakpoint.
- Semua teks lolos kontras AA.
- Halaman bisa dipakai dengan keyboard.
- Tidak ada error console.
- Tidak ada klaim atau data karangan.
- `DESIGN.md` dan `PLAN.md` ada di repo.
