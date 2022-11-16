**Nama : Meyda Wikaromah**

**Nim : 2110131220015**

**Mata Kuliah : Pemrosesan Citra Digital**

## **Bit-plane Slicing**

Bit-plane slicing merupakan metode yang digunakan untuk melihat konstribusi atau pengaruh tiap bit penyusun citra. Untuk citra 8 bit, pada dasarnya tiap intensitas yang nilainya dalam format decimal, bisa dipecah menjadi bit-bit dalam format biner. Misalnya, sebuah pixel dengan intensitas 245 (decimal) bila dijadikan biner adalah 11110101.

- Tujuan: Menonjolkan kontribusi dari bit tertentu di dalam citra.

- Misalkan satu pixel = 8 bit. Bit-bit tersusun dari kiri ke kanan dalam urutan yang kurang berarti (least significant bits atau LSB) hingga bit-bit yang berarti (most significant bits atau MSB).

- Susunan bit pada setiap byte adalah b7 b6 b5 b4 b3 b2 b1 b0

Contoh: 

<p align = "center">
    <img src = "gambar/bps.png">
</p>

- Jika setiap bit dari setiap pixel diambil, maka diperoleh 8 buah bidang
(bit-plane).

<p align = "center">
    <img src = "gambar/bps2.png">
</p>

Contoh :

<p align = "center">
    <img src = "gambar/bps3.png">
</p>

Contoh penerapan pada Octave :

Contoh :

<p align = "center">
    <img src = "gambar/bps4.png">
</p>

Contoh :

<p align = "center">
    <img src = "gambar/bps5.png">
</p>

## **Simple Steganografi**

**1. Pengertian Steganografi**

Steganografi atau Steganography adalah sebuah ilmu, teknik atau seni menyembunyikan sebuah pesan rahasia dengan suatu cara sehingga pesan tersebut hanya akan diketahui oleh si pengirim dan si penerima pesan.

Steganografi berasal dari Bahasa Yunani yaitu Stegano yang berarti “tersembunyi atau menyembunyikan” dan graphy yang berarti “tulisan".  Jadi Steganografi adalah tulisan atau pesan yang disembunyikan. Steganografi merupakan kebalikan dari Kriptografi yang menyamarkan arti dari sebuah pesan rahasia saja, tetapi tidak menyembunyikan bahwa ada sebuah pesan. Kelebihan Steganografi dibandingkan dengan Kriptografi adalah pesan-pesannya akan dibuat tidak menarik perhatian dan tidak menimbulkan kecurigaan, berbeda dengan Kriptografi yang pesannya tidak disembunyikan, walaupun pesannya sulit untuk di pecahkan akan tetapi itu akan menimbulkan kecurigaan terhadap pesan tersebut.

**2. Prinsip Kerja Steganografi**

Pesan rahasia yang akan disembunyikan disisipkan pada suatu media penampung seperti citra, suara, video dan sebagainya yang terlihat tidak mencurigakan untuk menyimpan pesan rahasia. Pesan rahasia akan memerlukan sebuah kunci rahasia yang dinamakan stego-key agar hanya pihak yang berhak saja yang dapat membuka pesan tersebut.

Contoh Penerapan Steganografi :

<p align = "center">
    <img src = "gambar/stg1.png">
    <img src = "gambar/stg2.png">
</p>

ini adalah citra asli sebelum disisipkan sebuah pesan :
<p align = "center">
    <img src = "gambar/catgray.jpg">
</p>

<p align = "center">
    (Gambar 1)
</p>

ini adalah citra baru setelah disisipkan sebuah pesan :
<p align = "center">
    <img src = "gambar/stego_image.png">
</p>

<p align = "center">
    (Gambar 2)
</p>

Dari dua gambar diatas terlihat seperti tidak ada perbedaan dari gambar tersebut. Padahal gambar 2 memiliki sebuah pesan rahasia didalamnya.

<p align = "center">
    <img src = "gambar/stego2.png">
</p>

<p align = "center">
    (Gambar 2.1)
</p>

Jika gambar 2 kita buat seperti tampilan di atas maka terlihat bagian garis putih adalah letak pesan rahasia yang kita sisipkan.





