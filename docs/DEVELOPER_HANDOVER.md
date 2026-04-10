# HENTPRO Developer Handover

Dokumen ini dibuat sebagai panduan tim dev berikutnya agar bisa memahami status terbaru website dan melanjutkan pengembangan dengan aman.

## 1. Scope Proyek Saat Ini

- Tech stack: HTML, CSS, JavaScript (single page static site)
- File utama aplikasi: `index.html`
- Folder aset gambar: `aset/`
- Tidak ada build system atau framework (langsung buka file HTML)

## 2. Struktur Section Final (Urutan Halaman)

Urutan section yang aktif saat ini:

1. HOME (`#home`)
2. ABOUT US (`#about`)
3. OUR SERVICES (`#services`)
4. VISION, MISSION & CORE VALUES (`#vision`)
5. OUR CLIENTS (`#client-segments`)
6. CLIENTS - logo carousel (`#clients`)
7. OUR TEAM (`#team`)
8. FAQ (`#qna`)
9. CONTACT US (`#contact`)
10. FORM (`#form-section`)

## 3. Status Navbar

Desktop navbar:

- Main menu (5 item): HOME, ABOUT US, OUR SERVICES, VISION & MISSION, OUR CLIENTS
- Dropdown MORE: CLIENTS, OUR TEAM, FAQ, CONTACT US, FORM

Mobile nav:

- Mengikuti urutan section final

## 4. Perubahan Penting Terbaru

### 4.1 Vision, Mission & Core Values

- Card Vision dan Mission ditengah (`text-align: center`)
- Lebar area card dibuat penuh di dalam section (`.vm-container` full width)
- Card Core Values juga ditengah dan mengisi area section lebih optimal

### 4.2 Our Clients dan Our Team (Judul)

- Judul `Our Clients` (`#client-segments-title`) di-center dan warna biru
- Judul `Our Team` (`#team-title`) di-center dan warna biru
- Judul section `Clients` (`#clients h2`) di-center dan warna biru

### 4.3 Clients Logo Carousel

- Section `#clients` sudah memakai auto-scroll carousel berbasis CSS:
  - Wrapper: `.clients-carousel`
  - Track: `.clients-track`
  - Animasi: `@keyframes clients-scroll`
- Logo digandakan 2x di track untuk efek loop halus
- Hover pada carousel akan pause animasi

Catatan teknis:
- Panjang translasi animasi saat ini memakai nilai tetap: `translateX(calc(-198px * 10))`
- Jika jumlah logo berubah, nilai ini perlu disesuaikan agar loop tetap mulus

### 4.4 Contact Us

- Text brand pada kartu kontak: `HENTPRO` (uppercase)
- Warna title HENTPRO dibuat biru
- Label Fax dibuat warna emas dengan class `.fax-label`

## 5. Lokasi Kode Penting

Silakan cek di `index.html`:

- Navbar dan header: sekitar area `<header>`
- Vision/Mission/Core Values: section `#vision`
- Our Clients segment: section `#client-segments`
- Clients carousel: section `#clients`
- Team: section `#team`
- FAQ: section `#qna`
- Contact info card: section `#contact`
- CSS utama: blok `<style>` di atas file

## 6. Cara Menjalankan Proyek Lokal

Karena static site:

- Opsi cepat: buka `index.html` langsung di browser
- Opsi dev server (direkomendasikan): pakai Live Server di VS Code

## 7. Rekomendasi Lanjutan untuk Tim Berikutnya

1. Refactor carousel menjadi data-driven JS (agar tidak perlu duplikasi logo manual)
2. Standarkan typography dan spacing token agar lebih konsisten antar section
3. Tambahkan smoke test visual sederhana (check section existence + nav anchors)
4. Pisahkan CSS/JS dari `index.html` ke file terpisah (`styles.css`, `main.js`) untuk maintainability

## 8. Checklist Sebelum Push ke GitHub

1. Pastikan perubahan file sudah sesuai
2. Cek site di desktop + mobile width
3. Verifikasi semua link navbar scroll ke section benar
4. Commit dengan pesan jelas

Contoh command:

```bash
git add index.html docs/DEVELOPER_HANDOVER.md
git commit -m "docs: add developer handover and latest section updates"
git push origin <branch-name>
```

## 9. Catatan Handover

Jika ada perubahan section order atau item navbar lagi, update dokumen ini agar tim berikutnya tidak kehilangan konteks.
