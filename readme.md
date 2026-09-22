# Lyrics to ASCII Art Visualizer

Project simpel berbasis HTML, CSS, dan JavaScript murni untuk mengubah lirik lagu menjadi animasi teks ASCII Art secara dinamis. oh ya btw ini projek masi belum yg gua kembangkan seperti yg di vt tiktok, jadi bebas kalian mau kembangkan ini lebih bagus jg

## Cara Pakai
Sangat mudah dan tidak butuh instalasi Node.js atau server apa pun:
1. Download atau clone repository ini.
2. Buka file `index.html` di browser (Chrome, Safari, Firefox, dll).
3. Selesai! Animasi lirik akan langsung berjalan.

## Cara Custom Lirik & Setting
Kalian bisa mengatur lirik, waktu, dan warnanya sendiri. Buka file `index.html` menggunakan text editor (VSCode, Sublime, Notepad) dan cek baris-baris berikut:

### 1. Ubah Lirik dan Waktu (Sekitar Baris 62)
Cari tulisan `const config = {`. Di bagian ini kalian bisa mengatur teks dan durasinya satu per satu:
- `text`: Kalimat lirik yang ingin ditampilkan.
- `showMs`: Lama teks muncul di layar (dalam hitungan milidetik, 2000 = 2 detik).
- `hideMs`: Jeda waktu kosong (hitam) sebelum lirik selanjutnya muncul.
- `isLooping`: Ubah menjadi `false` kalau tidak ingin liriknya mengulang terus-menerus.

### 2. Ubah Warna (Sekitar Baris 8)
Jika ingin mengganti tema warnanya, cari bagian `:root` di dalam tag `<style>`. Tinggal ganti kode hex warna (seperti `#ee75d2`) sesuai selera kalian.

### 3. Ubah Bentuk Karakter (Sekitar Baris 78)
Cari bagian `const charsFixed`. Array ini berisi urutan karakter dari yang paling tipis sampai yang paling tebal. Kalian bisa memodifikasi karakternya di sini untuk mendapatkan style ASCII yang berbeda.

## Bagaimana Cara Kerjanya?
Untuk yang penasaran dengan logikanya, kode ini bekerja dengan cara berikut:
1. **Render ke Hidden Canvas**: Script akan menulis lirik lagu ke dalam sebuah `<canvas>` yang sebenarnya disembunyikan (`display: none`). Kodenya juga sudah dilengkapi sistem Word Wrap, jadi kalau liriknya panjang, akan otomatis turun ke baris baru dan posisinya selalu di tengah.
2. **Scan Data Pixel**: Script kemudian membaca tiap pixel dari teks di dalam canvas tersebut menggunakan fungsi `getImageData()`.
3. **Konversi ASCII**: Dari data RGB tadi, script menghitung tingkat kecerahan (brightness) tiap pixel. Pixel yang gelap akan di-render menjadi spasi transparan, dan pixel yang terang akan dipetakan menjadi salah satu karakter dari array `charsFixed`. Hasilnya langsung dicetak ke layar dalam bentuk elemen `<span>` berwarna.

---

Bebas untuk dipakai dan dimodifikasi. Kalau kalian memakai kode ini untuk project kalian atau ingin berdiskusi lebih lanjut, silakan mampir dan tag gw di:

- **TikTok:** [@idfcauuu](https://www.tiktok.com/@idfcauuu)
- **Instagram:** [@thallatb](https://www.instagram.com/thallatb)

