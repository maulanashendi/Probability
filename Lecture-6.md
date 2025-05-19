# **Paradoks Probabilitas dan Inferensi: Menyatukan Monty Hall, Simpson’s Paradox, Hukum Probabilitas Total, dan Teorema Bayes**
Based on Statistics 110 by Prof. Joe Blitzstein – Harvard University

**Abstrak:**
Dalam studi probabilitas dan statistik, sering kali intuisi manusia gagal menangkap logika matematis yang mendasari pengambilan keputusan berbasis data. Artikel ini membahas dua kasus klasik — *Monty Hall Problem* dan *Simpson’s Paradox* — serta menguraikan bagaimana *Hukum Probabilitas Total*, *Teorema Bayes*, dan konsep *variabel perancu* memberikan kerangka berpikir matematis untuk menavigasi situasi tersebut.

---

## **1. Pendahuluan**

Statistik bukan hanya sekumpulan rumus, melainkan cara berpikir tentang ketidakpastian dan pengambilan keputusan. Dua fenomena — Monty Hall Problem dan Simpson’s Paradox — memperlihatkan bagaimana hasil yang tampak berlawanan dengan intuisi sebenarnya konsisten secara matematis. Pemahaman terhadap konsep dasar seperti hukum probabilitas total dan teorema Bayes sangat krusial dalam menjelaskan fenomena-fenomena ini secara rasional.

---

## **2. Monty Hall Problem: Mengubah Probabilitas Lewat Informasi Baru**

### Deskripsi Masalah:

Dalam permainan ini, peserta memilih satu dari tiga pintu. Di balik satu pintu terdapat mobil, dan dua lainnya kambing. Setelah peserta memilih, pembawa acara (yang tahu isi pintu) membuka salah satu pintu yang tidak dipilih dan berisi kambing. Peserta kemudian diberi pilihan untuk tetap pada pintu awal atau berpindah ke pintu lain yang tersisa.

### Hukum Probabilitas Total dalam Monty Hall:

Probabilitas menang jika tetap pada pilihan awal adalah 1/3. Namun, jika peserta berpindah, probabilitas menang menjadi 2/3. Ini dijelaskan oleh hukum probabilitas total, dengan mempertimbangkan semua kemungkinan awal (memilih mobil atau kambing) dan pengaruh dari aksi pembawa acara.

$$
P(\text{Menang jika pindah}) = P(\text{Awalnya pilih kambing}) = \frac{2}{3}
$$

### Teorema Bayes dalam Monty Hall:

Ketika satu pintu dibuka (menunjukkan kambing), kita memperoleh informasi baru. Teorema Bayes digunakan untuk memperbarui probabilitas bahwa mobil berada di salah satu pintu yang tersisa. Ini menjelaskan mengapa berpindah meningkatkan peluang menang.

---

## **3. Simpson’s Paradox: Ketika Agregasi Menyesatkan**

### Definisi:

Simpson’s Paradox terjadi ketika tren yang terlihat dalam kelompok data individual menghilang atau bahkan berbalik ketika data digabungkan. Hal ini terjadi karena adanya *variabel perancu* yang tidak diperhitungkan dalam analisis agregat.

### Contoh:

Dalam kasus penerimaan mahasiswa pascasarjana di UC Berkeley, data agregat menunjukkan bahwa pria lebih banyak diterima daripada wanita. Namun, ketika data dianalisis per departemen, ditemukan bahwa sebagian besar departemen sebenarnya lebih sering menerima pelamar wanita. Variabel perancu di sini adalah departemen—wanita cenderung melamar ke departemen yang lebih kompetitif dengan tingkat penerimaan rendah.

### Hukum Probabilitas Total dalam Simpson’s Paradox:

Perhitungan agregat seperti:

$$
P(\text{Diterima}) = \sum_{\text{Dept}} P(\text{Diterima} \mid \text{Dept}) \cdot P(\text{Dept})
$$

bisa sangat menyesatkan jika distribusi pelamar antar-departemen tidak seimbang antar subpopulasi.

### Teorema Bayes dalam Simpson’s Paradox:

Bayes dapat digunakan untuk mengevaluasi bagaimana probabilitas berubah ketika kita melihat dari perspektif yang berbeda: misalnya, menghitung probabilitas seseorang berjenis kelamin wanita mengingat mereka diterima, dibandingkan dengan sebaliknya.

---

## **4. Hukum Probabilitas Total dan Teorema Bayes: Hubungan dan Perbedaan**

### Hukum Probabilitas Total:

Digunakan untuk menghitung probabilitas total suatu peristiwa dengan menjumlahkan probabilitas bersyarat dari semua skenario yang mungkin terjadi.

$$
P(A) = \sum_{i=1}^n P(A \mid B_i) \cdot P(B_i)
$$

### Teorema Bayes:

Digunakan untuk membalik arah inferensi: dari akibat ke penyebab. Ini memungkinkan kita untuk memperbarui kepercayaan (prior) menjadi kepercayaan baru (posterior) setelah memperoleh bukti.

$$
P(A \mid B) = \frac{P(B \mid A) \cdot P(A)}{P(B)}
$$

### Perbedaan:

* Hukum Probabilitas Total bersifat **maju** (forward), digunakan untuk membangun $P(B)$ dari $P(B \mid A_i)$.
* Teorema Bayes bersifat **mundur** (inverse), digunakan untuk menyimpulkan $P(A \mid B)$ dari $P(B \mid A)$.

Meskipun sering digunakan bersama, keduanya menjawab pertanyaan yang berbeda.

---

## **5. Variabel Perancu: Sumber Potensi Bias**

Variabel perancu adalah variabel tersembunyi yang memengaruhi baik penyebab maupun akibat dalam suatu hubungan statistik. Jika tidak dikendalikan, variabel ini dapat menimbulkan kesimpulan kausal yang salah, sebagaimana yang terlihat dalam Simpson’s Paradox.

---

## **6. Kesimpulan**

Monty Hall Problem dan Simpson’s Paradox menunjukkan bahwa intuisi probabilistik sering kali keliru, dan bahwa alat-alat formal seperti hukum probabilitas total dan teorema Bayes sangat penting untuk memahami dan menavigasi ketidakpastian. Selain itu, mengenali peran variabel perancu sangat penting dalam membuat inferensi yang valid dari data.

Statistik bukan hanya soal angka — melainkan soal berpikir jernih dalam menghadapi keraguan.
