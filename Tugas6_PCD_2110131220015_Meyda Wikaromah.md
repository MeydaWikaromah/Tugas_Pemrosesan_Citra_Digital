**Nama : Meyda Wikaromah**

**Nim : 2110131220015**

**Mata Kuliah : Pemrosesan Citra Digital**

## **IMAGE ENHANCEMENT**

Image Enhancement (peningkatan kualitas citra) merupakan satu proses awal dalam pengolahan citra (preprocessing). Image Enhancement mengacu pada proses menyoroti informasi tertentu dari suatu citra, serta melemahkan atau menghapus informasi yang tidak perlu sesuai dengan kebutuhan tertentu. Misalnya, menghilangkan noise, mengungkapkan detail buram, dan menyesuaikan level untuk menyorot fitur gambar. Tujuan dari dilakukannya peningkatan kualitas citra adalah untuk memperoleh citra yang lebih sesuai digunakan untuk aplikasi lebih lanjut.

Proses-proses yang termasuk ke dalam peningkatan kualitas citra:

- Pengubahan kecerahan gambar (image brightening)

- Citra negatif (image negatives)

- Peregangan kontras (contrast stretching)

- Pengubahan histogram citra

- Pelembutan citra (image smoothing)

- Penajaman (sharpening) tepi (edge)

- Pewarnaan semu (pseudocolouring)

- Pengubahan geometrik

- dan lainnya.

Teknik peningkatan kualitas citra dapat dibagi menjadi dua kategori yaitu:

1. Domain Spasial : Peningkatan ruang gambar yang membagi gambar menjadi piksel yang seragam sesuai dengan koordinat spasial dengan resolusi tertentu. Metode domain spasial melakukan operasi pada piksel secara langsung.

2. Domain Frekuensi : Peningkatan yang diperoleh dengan menerapkan transformasi Fourier ke domain spasial. Dalam domain frekuensi, piksel dioperasikan dalam kelompok dan juga secara tidak langsung.

### **1. Domain Spasial**

Istilah domain spasial mengacu pada bidang gambar itu sendiri dan metode dalam kategori ini didasarkan pada direct manipulasi pixel dalam sebuah citra atau memanipulasi secara langsung pixel-pixel di dalam citra.

Metode pemrosesan citra dalam domain spasial dinyatakan sebagai:

<p align = "center">
    g(x,y) = T [ f(x,y) ]
</p>

Dimana :

- f(x,y) : citra input

- g(x,y) : citra output

- T adalah operator terhadap f. 

T bisa beroperasi pada satu pixel, sekelompok pixel bertetangga, atau keseluruhan pixel di dalam citra. Jadi, metode dalam domain spasial dapat dilakukan pada aras titik (pixel), aras
lokal, dan aras global. 


<p align = "center">
    <img src = "gambar/T1.png">
</p>

<p align = "center">
    (T beroperasi pada satu pixel)
</p>

<p align = "center">
    <img src = "gambar/T2.png">
</p>

<p align = "center">
    (T beroperasi pada sekelompok pixel bertetangga)
</p>

<p align = "center">
    <img src = "gambar/T3.png">
</p>

<p align = "center">
    (T beroperasi pada keseluruhan pixel di dalam citra)
</p>

**Pemrosesan dalam aras titik**

- g(x,y) = T [ f(x,y) ]

- T hanya beroperasi pada satu pixel

<p align = "center">
    <img src = "gambar/arastitik.png">
</p>

- T adalah fungsi transformasi nilai grayscale, sehingga ditulis:

s = T(r)

dimana :

r : variabel yang menyatakan nilai grayscale f(x,y) 

s : variabel yang menyatakan nilai grayscale g(x,y) 

Contoh-contoh image enhancement dalam aras titik:

1. Mencerahkan citra (image brightening)

2. Menegatifkan citra (image negatives)

3. Peregangan kontras (contrast stretching)

4. Gamma correction

5. dll


**1. Pencerahan citra (image brightening)**

Kecerahan citra dapat diperbaiki dengan menambahkan/mengurangkan sebuah konstanta kepada (atau dari) setiap pixel, atau mengalikan sebuah konstansta ke setiap pixel.

r = s + b

- Jika b positif, kecerahan citra bertambah, jika b negatif kecerahan citra berkurang

- Perlu operasi clipping jika nilai r + b berada di bawah nilai intensitas
minimum atau di atas nilai intensitas maksimum:

- jika r + b > 255, maka s = 255

- jika r + b < 0, maka s = 0

<p align = "center">
    <img src = "gambar/ib1.png">
</p>

Operasi pencerahan yang lain adalah menggunakan rumus:

r = as + b

a dan b adalah konstanta

**2. Menegatifkan citra (image negatives)**

- Seperti film negatif pada fotografi.

<p align = "center">
    <img src = "gambar/in0.png">
</p>

- Misalkan citra memiliki L derajat keabuan

- Caranya: kurangi nilai intensitas pixel dari nilai keabuan maksimum (L – 1)

s = (L – 1) – r 

Contoh pada citra grayscale 8-bit:

s = 255 – r

<p align = "center">
    <img src = "gambar/in01.png">
</p>

<p align = "center">
    <img src = "gambar/in1.png">
</p>

Sebagai proses image enhancement, menegatifkan citra bermanfaat
bila area hitam sangat dominan di dalam citra, misalnya foto sinar-X 
dan citra mammografi. 

<p align = "center">
    <img src = "gambar/in2.png">
</p>

<p align = "center">
    <img src = "gambar/in3.png">
</p>

<p align = "center">
    <img src = "gambar/cn1.png">
</p>

- Menegatifkan citra adalah salah satu transformasi linier. Selain
transformasi linier, terdapat tiga fungsi transformasi dasar keabuan:

1. Fungsi linier

- Transformasi negative dan 
transformasi identitas

2. Fungsi logaritma

- Transformasi log dan 
inverse-log

3. Fungsi pangkat

- Transformasi pangkat n 
dan transformasi akar
pangkat n

**Gamma correction**

- Contoh gamma correction :

<p align = "center">
    <img src = "gambar/gamma.png">
</p>

- Untuk melinierkan respons CRT diperlukan rangkaian pra-distorsi 

s = cr^1/Y

<p align = "center">
    <img src = "gambar/gamma2.png">
</p>

- Cathode ray tube (CRT) perangkat memiliki respons intensitas terhadap tegangan yaitu a fungsi daya, dengan Y
bervariasi dari 1,8 hingga 2,5

- Gambar akan menjadi lebih gelap.

- Koreksi gamma selesai
dengan melakukan preprocessing gambar
sebelum memasukkannya ke
monitor dengan s = cr^1/Y


**3. Perbaikan kontras (contrast enhancement)**

<p align = "center">
    <img src = "gambar/ic1.png">
</p>

- r = graylevel citra masukan

- s = graylevel citra luaran

- T = fungsi perbaikan kontras

- m = nilai ambang

Pada (a) Nilai-nilai pixel < m dibuah lebih gelap, nilai-nilai pixel >= m dibuat lebih terang. Operasi peregangan kontras (contrast stretching).

Pada (b) Nilai-nilai pixel < m dibuah menjadi hitam, nilai-nilai pixel >= m dibuah menjadi putih. Operasi pengambangan (thresholding).

<p align = "center">
    <img src = "gambar/pk1.png">
</p>

**Peregangan kontras (contrast stretching)**

• Tujuan: meningkatkan rentang nilai-nilai keabuan untuk citra kontrasrendah (terentang dari 0 sampai 255 pada citra 8-bit)

<p align = "center">
    <img src = "gambar/pk2.png">
</p>

Citra kontras-rendah dihasilkan dari

- pencahayaan yang kurang

- kekurangan pada rentang dinamis di dalam
imaging sensor

- kesalahan setting lensa selama akuisisi gambar

<p align = "center">
    <img src = "gambar/pk3.png">
</p>

• Lokasi (r1,s1) dan (r2,s2) menentukan bentuk fungsi transformasi.

• Jika r1= s1 dan r2= s2 maka transformasi adalah fungsi linier sehingga tidak menghasilkan perubahan.

• Jika r1=r2, s1=0 dan s2=L-1, transformasi menjadi fungsi pengambangan yang menghasilkan citra biner.

• Nilai-nilai di antara (r1,s1) and (r2,s2) menghasilkan penyebaran nilai keabuan citra luaran.

• Umumnya diasumsikan r1≤r2 dan s1≤s2

• Peregangan kontras dapat dilakukan dengan rumus berikut:

<p align = "center">
    <img src = "gambar/pk4.png">
</p>

<p align = "center">
    <img src = "gambar/pk5.png">
</p>

atau menggunakan rumus clipping berikut:

<p align = "center">
    <img src = "gambar/pk6.png">
</p>

<p align = "center">
    <img src = "gambar/pk7.png">
</p>

**4. Gray-level Slicing**

- Tujuan: menonjolkan (highlight) rentang keabuan tertentu di dalam
citra. 

- Contoh: menonjolkan gumpalan air yang ada pada citra satelit, 
menonjolkan cacat yang ada pada citra sinar X. 

- Dua pendekatan di dalam graylevel slicing :

1. Menampilkan lebih terang semua graylevel di 
dalam rentang yang ingin ditonjolkan, dan 
menampilkan lebih gelap semua graylevel lainnya
(‘discard background’).

2. Menampilkan lebih terang semua graylevel
di dalam rentang yang ingin ditonjolkan, 
sembari tetap mempertahankan graylevel
lainya (‘preserve background’).

<p align = "center">
    <img src = "gambar/gls.png">
</p>

<p align = "center">
    <img src = "gambar/gls2.png">
</p>

<p align = "center">
    <img src = "gambar/gls3.png">
</p>

**5. Bit-plane Slicing**

- Tujuan: Menonjolkan kontribusi dari bit tertentu di dalam citra.

- Misalkan satu pixel = 8 bit. Bit-bit tersusun dari kiri ke kanan dalam urutan
yang kurang berarti (least significant bits atau LSB) hingga bit-bit yang 
berarti (most significant bits atau MSB).

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

### **2. Domain Frekuensi**

- Konsep penyaringan lebih mudah divisualisasikan dalam frekuensi
domain. Oleh karena itu, peningkatan citra f (m,n) dapat dilakukan
dalam domain frekuensi, berdasarkan DFT F(u, v).

- Ini sangat berguna, jika perluasan spasial dari urutan penyebaran titik h(m, n) besar. Dalam hal ini, konvolusi mungkin secara komputasi tidak menarik.

<p align = "center">
    <img src = "gambar/fd1.png">
</p>

- Oleh karena itu, kita dapat secara langsung merancang fungsi transfer H (u, v) dan
mengimplementasikan peningkatan dalam domain frekuensi sebagai
berikut:

<p align = "center">
    <img src = "gambar/fd2.png">
</p>

**Lowpass filtering**

- Tepi dan transisi tajam dalam nilai abu-abu dalam gambar berkontribusi
signifikan terhadap konten frekuensi tinggi dari transformasi Fourier-nya.

- Wilayah dengan nilai abu-abu yang relatif seragam dalam sebuah gambar berkontribusi
ke konten frekuensi rendah dari transformasi Fourier-nya.

- Oleh karena itu, sebuah gambar dapat dihaluskan dalam domain Frekuensi dengan
melemahkan konten frekuensi tinggi dari transformasi Fourier-nya.
Ini akan menjadi filter lowpass.

- Untuk kesederhanaan, kami hanya akan mempertimbangkan filter yang nyata
dan simetri radial.

- Filter lowpass yang ideal dengan frekuensi cutoff r0 :

<p align = "center">
    <img src = "gambar/fd3.png">
</p>

<p align = "center">
    <img src = "gambar/fd4.png">
</p>

- Perhatikan bahwa titik asal (0, 0) berada di tengah dan bukan di sudut
gambar (ingat operasi "fftshift").

- Transisi mendadak dari 1 ke 0 dari fungsi transfer
H (u,v) tidak dapat diwujudkan dalam praktik, menggunakan elektronik
komponen. Namun, itu dapat disimulasikan di komputer.

<p align = "center">
    <img src = "gambar/fd5.png">
</p>

- Perhatikan efek dering yang parah pada gambar buram, yang
merupakan karakteristik filter ideal. Hal ini karena diskontinuitas
dalam fungsi transfer filter.

**Butterworth lowpass filter**

Filter lowpass Butterworth dua dimensi memiliki transfer
fungsi:

<p align = "center">
    <img src = "gambar/fd6.png">
</p>

<p align = "center">
    <img src = "gambar/fd7.png">
</p>

- Respons frekuensi tidak memiliki transisi yang tajam seperti pada
LP yang ideal.

- Ini lebih sesuai untuk penghalusan gambar daripada yang ideal
LPF, karena ini tidak memperkenalkan dering.

<p align = "center">
    <img src = "gambar/fd8.png">
</p>

<p align = "center">
    <img src = "gambar/fd9.png">
</p>

<p align = "center">
    <img src = "gambar/fd10.png">
</p>

**Highpass filtering**

• Tepi dan transisi tajam dalam nilai abu-abu dalam gambar berkontribusi
signifikan terhadap konten frekuensi tinggi dari transformasi Fourier-nya.

• Wilayah dengan nilai abu-abu yang relatif seragam dalam sebuah gambar berkontribusi
ke konten frekuensi rendah dari transformasi Fourier-nya.

• Oleh karena itu, penajaman gambar dalam domain Frekuensi dapat dilakukan
dengan melemahkan konten frekuensi rendah Fourier .-nya
mengubah. Ini akan menjadi filter highpass.

• Untuk mempermudah, kami hanya akan mempertimbangkan filter yang nyata
dan simetri radial.

• Filter highpass yang ideal dengan frekuensi cutoff r0 :

<p align = "center">
    <img src = "gambar/fd11.png">
</p>

<p align = "center">
    <img src = "gambar/fd12.png">
</p>

• Perhatikan bahwa titik asal (0, 0) berada di tengah dan bukan di sudut
gambar (ingat operasi "fftshift").

• Transisi tiba-tiba dari 1 ke 0 dari fungsi transfer
H (u,v) tidak dapat direalisasikan dalam praktek, menggunakan elektronik
komponen. Namun, itu dapat disimulasikan di komputer.

<p align = "center">
    <img src = "gambar/fd13.png">
</p>

• Perhatikan efek dering yang parah pada gambar keluaran, yang mana
adalah karakteristik dari filter yang ideal. Itu karena diskontinuitas
dalam fungsi transfer filter.

**Butterworth highpass filter**

• Filter highpass Butterworth dua dimensi memiliki transfer
fungsi:

<p align = "center">
    <img src = "gambar/fd14.png">
</p>

• n: urutan filter, r0: frekuensi cutoff

<p align = "center">
    <img src = "gambar/fd15.png">
</p>

• Respons frekuensi tidak memiliki transisi yang tajam seperti pada
HPF yang ideal.

• Ini lebih cocok untuk penajaman gambar daripada yang ideal
HPF, karena ini tidak menimbulkan dering.

<p align = "center">
    <img src = "gambar/fd16.png">
</p>