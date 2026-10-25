# Dennis Shop Design System

Etalase langganan Dennis Shop. Isi: Spotify Premium Family dan iCloud+ 2 TB, per bulan.

## Karakter

Lembar harga cetak. Sederhana, jujur, dan jelas. Bukan landing page SaaS.

Dial: **ENERGY 2 / RHYTHM 2 / MOTION 1**

- **ENERGY 2:** karakter kuat dari tipografi dan harga besar, tanpa gradient atau glow.
- **RHYTHM 2:** intro asimetris, dua baris harga, lalu blok cara pesan. Tidak seragam.
- **MOTION 1:** hanya hover, focus, dan transisi warna. Tidak ada animasi scroll.

## Palette

| Peran | Hex | Pakai untuk |
|---|---|---|
| Latar | `#F4EFE5` | Seluruh halaman |
| Teks utama | `#191713` | Heading, harga, teks utama |
| Teks sekunder | `#5E574C` | Meta, nomor urut, deskripsi |
| Aksen | `#B83B1D` | Link, hover, focus ring, marker daftar |

Kontras:

- Ink di paper: 15.62:1
- Muted di paper: 6.23:1
- Accent di paper: 4.98:1

Semua teks memenuhi WCAG AA. Aksen hanya dipakai untuk elemen yang benar-benar perlu perhatian, bukan untuk seluruh halaman.

Warna brand Spotify dan iCloud tidak dipakai sebagai warna halaman. Logo produk dipakai teks saja, tanpa file gambar.

## Tipografi

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
- Body: 17px, line-height 1.6.
- Nav: 15px, weight 500.
- Teks sekunder: 14 atau 15px.

## Layout

- Max width: `1120px`.
- Gutter: `clamp(20px, 5vw, 64px)`.
- Intro: grid 8 kolom untuk H1, 4 kolom untuk subline di desktop.
- Baris harga di desktop: `3.5rem minmax(0,1fr) minmax(24px,1fr) auto max-content`.
- Di layar kecil, baris harga bertumpuk.
- Spasi section tidak seragam. Intro lebih lega, price board lebih rapat.
- Tanpa `100vh` section.
- Tanpa horizontal scroll.

## Motif Identitas

Garis titik-titik menghubungkan nama paket dan harga. Ini motif identitas halaman, bukan dekorasi acak.

Garis utama memakai 1px solid. Garis pemisah baris memakai warna `--rule`. Garis titik-titik memakai warna `--rule-strong`.

## Bentuk

- Radius: 4px sampai 6px. Bukan pill.
- Shadow: tidak ada.
- Gradient: tidak ada.
- Glassmorphism: tidak ada.
- Glow: tidak ada.
- Motion: hover, focus, dan transisi warna 150ms.
- Hormati `prefers-reduced-motion`.

## Komponen

- **Header:** wordmark `Dennis Shop` di kiri, nav `Harga`, `Cara pesan`, `WhatsApp` di kanan. Di layar kecil, nav turun ke baris kedua. Tidak memakai hamburger.
- **Price row:** nominal `01` atau `02`, nama produk, meta durasi, garis titik-titik, harga, CTA `Tanya paket`.
- **Cara pesan:** satu blok pendek berisi dua langkah nyata, bukan tiga kartu ikon.
- **Footer:** satu baris, tahun, link WhatsApp, catatan merek.

## Copy

- CTA: `Tanya paket`, `Chat WhatsApp`. Bukan generik seperti `Get Started`, `Learn More`, atau `Try Now`.
- Tidak ada statistik, testimoni, atau FAQ karangan.
- Tidak ada em dash.
- Semua link menuju section yang ada atau eksternal yang nyata. Tidak ada nav mati.

## Tema

Light theme permanen. Alasannya konsep kertas harga dan struk. Bukan dark mode default tanpa alasan. Tidak ada toggle tema.

## Kontrol Halaman

Tanpa JavaScript. Semua nav, anchor, dan link WhatsApp bekerja tanpa script.
