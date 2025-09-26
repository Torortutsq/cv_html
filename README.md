# Laporan Praktikum — Semantic HTML & CSS

**Nama:** I Gede Nada Arsana  
**NIM:** 42430011  
**Program Studi:** Teknologi Informasi — Fakultas Teknik dan Informatika, Universitas Pendidikan Nasional  
**Tahun:** 2025

---

## 1. Pendahuluan
**Semantic HTML** adalah praktik penggunaan markup HTML yang memberi makna jelas terhadap tipe konten sehingga browser, pembaca layar (assistive technologies), dan mesin pencari dapat memahami konteks serta struktur halaman web dengan lebih baik.  
Contoh elemen semantik yang umum digunakan antara lain:

- `<header>`: kepala halaman atau suatu bagian (dapat berisi judul, logo, form pencarian).  
- `<footer>`: kaki halaman/bagian (umumnya berisi hak cipta, kontak, dan tautan penting).  
- `<article>`: konten independen yang bisa didistribusikan/di-*reuse* (mis. artikel, posting blog).  
- `<section>`: bagian tematik dalam dokumen (idealnya memiliki judul).  
- `<nav>`: pembungkus komponen navigasi utama (mis. menu tautan).

Penggunaan elemen semantik membantu aksesibilitas dan **SEO**, serta membuat struktur kode lebih terorganisasi dibanding hanya memakai elemen non-semantik seperti `<div>` dan `<span>`.

---

## 2. Pembahasan

### 2.1 Struktur HTML (Contoh)
Berikut kerangka halaman CV sederhana menggunakan elemen semantik dan navigasi *in-page*:

```html
<header>
  <h1 style="color: aliceblue">Nada Arsana</h1>
  <p style="color: rgb(0, 94, 255)">Web Developer · Graphic Designer</p>
</header>
```
Penjelasan Kode :<br>
-header: Membuka bagian kepala halaman, berisi identitas atau judul.<br>
-h1 style="color: aliceblue">: Judul utama dengan warna teks aliceblue, berisi nama "Nada Arsana".<br>
-p style="color: rgb(0, 94, 255")>: Paragraf dengan warna biru RGB, berisi deskripsi "Web DeveloperGraphic`Designer".<br>
-header: Menutup elemen header.

```html
<nav class="navbar">
  <ul class="nav-list">
    <li class="nav-item"><a class="nav-link" href="#biodata">Biodata</a></li>
    <li class="nav-item"><a class="nav-link" href="#pendidikan">Pendidikan</a></li>
    <li class="nav-item"><a class="nav-link" href="#skills">Skills</a></li>
  </ul>
</nav>
```
Penjelasan Kode :<br>
-nav class="navbar": Menggunakan tag semantik nav untuk membungkus komponen navigasi utama. <br>
-class="navbar" digunakan untuk penataan gaya (styling).<br>
-ul class="nav-list": Membuat daftar tak berurutan (ul) untuk menampung link navigasi.<br>
-li class="nav-item": Setiap item daftar (li) adalah satu link navigasi.<br>
-a class="nav-link" href="#...": Link (a) menggunakan URL fragmen (#biodata, #pendidikan, dll.) yang akan menautkan ke <section> dengan id yang sesuai di halaman yang sama, menciptakan navigasi dalam halaman.

```html
<section id="biodata">
  <h2>Biodata Diri</h2>
  <p id="email">Email: <a href="mailto:igedenadaarsana@gmail.com">igedenadaarsana@gmail.com</a></p>
</section>
```
Penjelasan Kode : <br>
-section id="biodata": Menggunakan tag semantik section untuk mendefinisikan bagian yang berhubungan dengan tema "Biodata". <br>
-id="biodata" digunakan sebagai target tautan navigasi dan untuk styling.<br>
-(h2) Biodata Diri (h2): Judul untuk bagian ini, seperti yang disarankan untuk penggunaan section.<br>
-p id="email"...p: Paragraf yang berisi informasi kontak email. id="email" digunakan untuk memberikan gaya spesifik pada bagian ini di CSS. href="mailto:..." akan membuka klien email ketika link diklik. <br>

```html
<section id="pendidikan">
  <h2>Pendidikan</h2>
  <ul>
    <li>SDN 4 Sanur</li>
    <li>SMP Petra Berkat</li>
    <li>SMK Harapan</li>
  </ul>
</section>
```
Penjelasan Kode : <br>
-section id="pendidikan": Bagian tematik lain yang berisi riwayat pendidikan.<br>
-(h2) Pendidikan (h2): Judul bagian.<br>
-ul...ul: Daftar tak berurutan untuk mencantumkan riwayat sekolah/pendidikan.

```html
<section id="skills">
  <h2>Skills</h2>
  <p>HTML, CSS, JavaScript, ...</p>
</section>
```
Penjelasan Kode : <br>
-section id="skills": Bagian tematik yang merangkum kemampuan atau keahlian.<br>
-(h2) Skills (h2) : Judul bagian.

```html
<footer>
  <p>© 2025 Nada Arsana</p>
</footer>
```
Penjelasan Kode : <br>
-background-color: lightgray; - Memberikan warna latar belakang abu-abu muda pada footer <br>
-padding: 10px; - Memberikan ruang dalam 10px di semua sisi footer<br>
-text-align: center; - Meratakan semua konten di dalam footer ke tengah

```html
<header>
  <h1 style="color: aliceblue">Nada Arsana</h1>
  <p style="color: rgb(0, 94, 255)">Web Developer · Graphic Designer</p>
</header>

<nav class="navbar">
  <ul class="nav-list">
    <li class="nav-item"><a class="nav-link" href="#biodata">Biodata</a></li>
    <li class="nav-item"><a class="nav-link" href="#pendidikan">Pendidikan</a></li>
    <li class="nav-item"><a class="nav-link" href="#skills">Skills</a></li>
  </ul>
</nav>

<section id="biodata">
  <h2>Biodata Diri</h2>
  <p id="email">Email: <a href="mailto:igedenadaarsana@gmail.com">igedenadaarsana@gmail.com</a></p>
</section>

<section id="pendidikan">
  <h2>Pendidikan</h2>
  <ul>
    <li>SDN 4 Sanur</li>
    <li>SMP Petra Berkat</li>
    <li>SMK Harapan</li>
  </ul>
</section>

<section id="skills">
  <h2>Skills</h2>
  <p>HTML, CSS, JavaScript, ...</p>
</section>

<footer>
  <p>© 2025 Nada Arsana</p>
</footer>
```

**Penjelasan singkat:**
- `<nav class="navbar">` membungkus navigasi utama. Tautan pada `<a href="#...">` menargetkan `<section id="...">` terkait.  
- `id="email"` memberi *hook* spesifik untuk styling.  
- Setiap `<section>` bertema jelas dan memiliki heading (`<h2>`).

---

### 2.2 CSS (Konsep & Contoh)
#### a) Global dan *Typography*
```css
body { 
  font-family: Arial, sans-serif; 
  line-height: 1.5; 
}
```

#### b) Header
```css
header {
  background-color: lightgray;
  padding: 20px;
  text-align: center;
}
header h1::first-line { font-size: 140%; font-weight: 800; }
header p::first-line  { font-variant: small-caps; }
```

#### c) Navigasi
```css
.navbar { margin: 14px 0; text-align: center; }

.nav-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: inline-block;
}

.nav-item { display: inline-block; margin: 0 10px; }

.nav-link {
  text-decoration: none;
  color: #3f51b5;
}

.nav-link:hover {
  background: #3f51b5;
  color: #fff;
  text-decoration: underline;
}
```

#### d) Section (Box Model)
```css
section {
  border: 1px solid #ddd;
  padding: 15px;
  margin: 20px 0;
  box-shadow: 0 0 5px #aaa;
}
```

#### e) Email (Selektor ID dan Link)
```css
#email { font-weight: 700; color: #3f51b5; }
#email a { text-decoration: none; }
```

#### f) Footer
```css
footer {
  background-color: lightgray;
  padding: 10px;
  text-align: center;
}
```

#### g) Selektor Atribut & Pseudo-element
```css
/* menambahkan ikon setelah link sosmed tertentu */
a[href*="instagram.com"]::after { content: "📷"; display: inline-block; font-size: 10px; vertical-align: text-top; }
a[href*="tiktok.com"]::after    { content: "🎵"; display: inline-block; font-size: 10px; vertical-align: text-top; }
```

---

## 3. Kesimpulan
**Semantic HTML** membuat struktur halaman lebih jelas, aksesibel, dan ramah SEO. Dikombinasikan dengan **CSS** (selektor, *box model*, dan *pseudo classes/elements*), tampilan menjadi konsisten, teratur, dan mudah dirawat dibanding hanya mengandalkan `<div>`/`<span>` non-semantik.

---

## 4. Lampiran
- Tambahkan tangkapan layar hasil halaman, atau *link* demo bila tersedia.
- Simpan CSS ke berkas terpisah (`style.css`) untuk pemeliharaan yang lebih baik.
```html
<link rel="stylesheet" href="style.css" />
```
