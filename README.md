# Laporan Praktikum — Semantic HTML & CSS

**Nama:** I Gede Nada Arsana  
**NIM:** 42430011  
**Program Studi:** Teknologi Informasi — Fakultas Teknik dan Informatika, Universitas Pendidikan Nasional  
**Tahun:** 2025

---

1. Pendahuluan
**Semantic HTML** adalah praktik penggunaan markup HTML yang memberi makna jelas terhadap tipe konten sehingga browser, pembaca layar (assistive technologies), dan mesin pencari dapat memahami konteks serta struktur halaman web dengan lebih baik.  
Contoh elemen semantik yang umum digunakan antara lain:

- `<header>`: kepala halaman atau suatu bagian (dapat berisi judul, logo, form pencarian).  
- `<footer>`: kaki halaman/bagian (umumnya berisi hak cipta, kontak, dan tautan penting).  
- `<article>`: konten independen yang bisa didistribusikan/di-*reuse* (mis. artikel, posting blog).  
- `<section>`: bagian tematik dalam dokumen (idealnya memiliki judul).  
- `<nav>`: pembungkus komponen navigasi utama (mis. menu tautan).

Penggunaan elemen semantik membantu aksesibilitas dan **SEO**, serta membuat struktur kode lebih terorganisasi dibanding hanya memakai elemen non-semantik seperti `<div>` dan `<span>`.

---

2. Pembahasan

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

---

```css
body { 
  font-family: Arial, sans-serif; 
  line-height: 1.5; 
}
```
Penjelasan Kode : <br>
-Menetapkan gaya font default untuk seluruh konten di dalam tag <body> menjadi Arial; jika Arial tidak tersedia, akan menggunakan font generik sans-serif.

```css
header {
  background-color: lightgray;
  padding: 20px;
  text-align: center;
}
header h1::first-line { font-size: 140%; font-weight: 800; }
header p::first-line  { font-variant: small-caps; }
```
Penjelasan Kode : <br>
-header: Menetapkan latar belakang abu-abu terang (Lightgray), jarak dalam (padding) 20px, dan meratakan teks di dalamnya ke tengah (center) untuk elemen header (kepala halaman/bagian).<br>
-header h1::first-line: Menggunakan pseudo-element ::first-line untuk membuat baris pertama dari elemen h1 di dalam header menjadi 140% lebih besar dari ukuran font normal dan sangat tebal (800).<br>
-header p::first-line: Menggunakan ::first-line untuk membuat baris pertama dari paragraf (p) di dalam header menggunakan huruf kapital kecil (small-caps).


```css
.navbar { margin: 14px 0; text-align: center; }
```
Penjelasan Kode : <br>
-margin: 14 0;: Menetapkan margin atas dan bawah 14 unit (kemungkinan dimaksudkan 14px atau unit lain) dan margin kiri-kanan 0.<br>
-text-align: center;: Memposisikan konten di dalam navbar (yaitu daftar link) di tengah.

```css
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
Penjelasan Kode : <br>
-.nav-list (Tag ul):
list-style: none;: Menghapus bullet point default dari daftar.
padding: 0; margin: 0;: Menghilangkan padding dan margin bawaan pada daftar.
display: inline-block;: Memungkinkan daftar untuk disejajarkan di tengah (berkat text-align: center; pada .navbar) dan tetap memperhitungkan lebar dan tinggi.<br>
-.nav-item (Tag li):
display: inline-block;: Mengubah item daftar agar ditampilkan berdampingan (horizontal) alih-alih di baris baru.
margin: 0 10;: Memberikan sedikit jarak ke kiri dan kanan antar item (kemungkinan dimaksudkan 10px).<br>
-.nav-link (Tag a):
text-decoration: none;: Menghapus garis bawah default dari link.
color: #3f51b5;: Mengatur warna link menjadi biru keunguan gelap.<br>
-.nav-link:hover: Menetapkan gaya saat kursor mengarah (hover) ke link: latar belakang menjadi warna biru tersebut, teks menjadi putih (#fff), dan garis bawah muncul kembali.


```css
section {
  border: 1px solid #ddd;
  padding: 15px;
  margin: 20px 0;
  box-shadow: 0 0 5px #aaa;
}
```
Penjelasan Kode : <br>
-border: 1px solid #ddd;: Memberikan garis tepi tipis (1px solid) berwarna abu-abu sangat terang.<br>
-padding: 15px;: Menambah jarak 15px di dalam setiap section.<br>
-margin: 20px 0;: Memberikan jarak 20px di atas dan bawah section untuk memisahkannya dari elemen lain.<br>
-box-shadow: 0 0 5px #aaa;: Menambahkan sedikit efek bayangan lembut berwarna abu-abu ke setiap section, membuatnya tampak menonjol.


```css
#email { font-weight: 700; color: #3f51b5; }
#email a { text-decoration: none; }
```
Penjelasan Kode : <br>
-#email (Tag p id="email"):<br>
-font-weight: 700;: Membuat teks pada paragraf email menjadi tebal.<br>
-color: #3f51b5;: Mengatur warna teks pada paragraf email menjadi biru keunguan gelap.<br>
-#email a (Tag <a> di dalam #email):<br>
-text-decoration: none;: Secara spesifik menghapus garis bawah hanya pada link email di dalam paragraf ini.

```css
footer {
  background-color: lightgray;
  padding: 10px;
  text-align: center;
}
```
Penjelasan Kode : <br>
-background-color: lightgray; - Memberikan warna latar belakang abu-abu muda pada footer <br>
-padding: 10px; - Memberikan ruang dalam 10px di semua sisi footer <br>
-text-align: center; - Meratakan semua konten di dalam footer ke tengah


```css
/* menambahkan ikon setelah link sosmed tertentu */
a[href*="instagram.com"]::after { content: "📷"; display: inline-block; font-size: 10px; vertical-align: text-top; }
a[href*="tiktok.com"]::after    { content: "🎵"; display: inline-block; font-size: 10px; vertical-align: text-top; }
```

---

3. Kesimpulan
**Semantic HTML** membuat struktur halaman lebih jelas, aksesibel, dan ramah SEO. Dikombinasikan dengan **CSS** (selektor, *box model*, dan *pseudo classes/elements*), tampilan menjadi konsisten, teratur, dan mudah dirawat dibanding hanya mengandalkan `<div>`/`<span>` non-semantik.

---

4. Lampiran
<img width="1470" height="838" alt="Tangkapan Layar 2025-09-26 pukul 21 52 23" src="https://github.com/user-attachments/assets/79512469-6404-4a5f-b015-355e89131220" />
