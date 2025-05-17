# **Lecture 3 — Birthday Problem & Properties of Probability**

Based on Statistics 110 by Prof. Joe Blitzstein – Harvard University

---

## **Pendahuluan**

Topik kuliah ini berfokus pada dua hal penting dalam probabilitas:

1. **Birthday Problem**: Sebuah contoh klasik probabilitas yang kontra-intuitif, namun sangat penting secara konsep dan aplikasi.
2. **Properti Probabilitas**: Memperluas pemahaman kita tentang aksioma probabilitas dan berbagai properti turunannya, termasuk prinsip inklusi-eksklusi.

Kuliah ini mengajarkan bahwa banyak kejadian dalam dunia nyata tidak bisa dimodelkan hanya dengan asumsi satu faktor penyebab. Kita belajar untuk berpikir secara sistemik dan mempertimbangkan gabungan dari berbagai faktor.

---

## **1. Birthday Problem**

### **Pertanyaan**

Dalam sebuah ruangan dengan n orang, berapa peluang bahwa ada minimal dua orang yang memiliki tanggal ulang tahun yang sama?

### **Asumsi**

* Terdapat 365 hari dalam setahun (tahun kabisat diabaikan).
* Setiap hari memiliki probabilitas yang sama untuk menjadi ulang tahun seseorang.
* Tanggal ulang tahun tiap orang dipilih secara independen.

### **Cara Penyelesaian: Melalui Komplemen**

Alih-alih menghitung langsung “ada yang ulang tahunnya sama”, kita hitung kebalikannya: **semua orang ulang tahunnya berbeda**, lalu kita kurangi dari 1.

$$
P(\text{ada yang sama}) = 1 - P(\text{semua berbeda})
$$

### **Perhitungan**

Jika ada n orang:

$$
P(\text{semua berbeda}) = \prod_{i=0}^{n-1} \left(1 - \frac{i}{365} \right)
$$

Interpretasinya:

* Orang ke-1 bebas memilih ulang tahun: 365/365
* Orang ke-2 harus berbeda dari yang pertama: 364/365
* Orang ke-3 harus berbeda dari dua sebelumnya: 363/365
* Dan seterusnya hingga orang ke-n: $\frac{365 - (n - 1)}{365}$

Itulah mengapa indeks i dalam produk dimulai dari 0 hingga n - 1.

### **Contoh Hasil**

Jika n = 23:

$$
P(\text{ada yang sama}) \approx 1 - 0.4927 = 0.5073
$$

Dengan hanya 23 orang dalam satu ruangan, probabilitas setidaknya dua orang memiliki ulang tahun yang sama sudah melebihi 50%. Ini tampak mengejutkan karena 23 jauh lebih kecil dari 365.

### **Penjelasan Intuitif**

Kunci dari fenomena ini adalah **jumlah pasangan unik** yang bisa terbentuk dari n orang. Untuk 23 orang, ada 253 pasangan unik. Semakin banyak pasangan, semakin besar peluang “bentrok” ulang tahun, meskipun jumlah total tanggal hanya 365.

---

## **2. Properti Dasar Probabilitas**

Tiga aksioma probabilitas yang diperkenalkan oleh Kolmogorov tetap menjadi dasar dalam setiap perhitungan probabilitas.

### **Aksioma Probabilitas**

1. **Non-negativitas**: Untuk setiap kejadian A, $P(A) \geq 0$
2. **Normalisasi**: Probabilitas ruang sampel adalah 1, $P(S) = 1$
3. **Adisitivitas**: Jika A dan B tidak terjadi bersamaan, maka $P(A \cup B) = P(A) + P(B)$

### **Properti Turunan**

* **Komplemen**: $P(A^c) = 1 - P(A)$
  Jika peluang suatu kejadian terjadi adalah 0.3, maka peluang kejadian itu tidak terjadi adalah 0.7.

* **Monotonisitas**: Jika A adalah subset dari B, maka $P(A) \leq P(B)$

* **Probabilitas Kosong**: Kejadian yang mustahil memiliki probabilitas nol, yaitu $P(\emptyset) = 0$

---

## **3. Prinsip Inklusi-Eksklusi**

Ketika dua atau lebih kejadian **tidak saling lepas**, kita tidak bisa menjumlahkan probabilitasnya begitu saja. Kita harus mengoreksi penghitungan ganda pada bagian yang tumpang tindih.

### **Untuk dua kejadian A dan B:**

$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

### **Untuk tiga kejadian A, B, C:**

$$
\begin{aligned}
P(A \cup B \cup C) &= P(A) + P(B) + P(C) \\
&- P(A \cap B) - P(A \cap C) - P(B \cap C) \\
&+ P(A \cap B \cap C)
\end{aligned}
$$

### **Makna Konseptual**

Jika Anda ingin menghitung jumlah orang yang suka pizza, sushi, dan kue dalam sebuah pesta, Anda tidak bisa hanya menjumlahkan masing-masing kategori. Banyak orang mungkin suka dua atau tiga makanan tersebut sekaligus. Prinsip inklusi-eksklusi adalah metode untuk menghitung jumlah total unik secara tepat dengan memperhitungkan tumpang tindih antar kelompok.

---

## **4. Aplikasi Nyata: Kriptografi dan Birthday Attack**

Birthday problem tidak hanya soal ulang tahun. Ia muncul dalam **kriptografi**, khususnya dalam **birthday attack**.

### **Ide Dasar:**

Jika ada N kemungkinan hasil hash (misalnya, dalam hash 64-bit ada 2⁶⁴ kemungkinan), maka Anda hanya perlu sekitar √N percobaan (yakni 2³²) untuk memiliki peluang signifikan menemukan dua input berbeda yang menghasilkan hash yang sama.

Itu sebabnya sistem kriptografi modern menggunakan hash dengan bit yang sangat panjang (misal SHA-256) agar probabilitas collision tetap kecil meskipun ada banyak percobaan.

---

## **5. Pendekatan Probabilistik untuk Prediksi Harga Pasar**

Dalam konteks pasar kripto atau saham, pendekatan probabilitas sangat berguna untuk memahami **kejadian yang saling tumpang tindih** dalam mendorong perubahan harga.

Alih-alih bertanya:

> “Apa satu faktor yang menyebabkan harga naik?”

Kita bisa bertanya:

> “Kejadian apa saja yang sering muncul **bersamaan** ketika harga naik?”

### **Langkah Umum:**

1. Identifikasi hari-hari ketika harga naik signifikan.
2. Tandai sinyal atau faktor yang aktif pada hari tersebut (misalnya RSI, MA crossover, volume spike).
3. Susun data dalam bentuk binary per hari (sinyal on/off).
4. Lakukan clustering atau segmentasi untuk menemukan pola sinyal yang berulang saat harga naik.
5. Hitung probabilitas gabungan dari pola-pola tersebut.

Ini adalah aplikasi prinsip birthday logic: ketika ada cukup banyak kejadian, tumpang tindih antar faktor menjadi sangat penting. Pola yang sering muncul bersamaan bisa memberi insight yang lebih kuat daripada hanya mengandalkan satu indikator teknikal.

---

## **Kesimpulan**

Lecture 3 menunjukkan bagaimana probabilitas bisa digunakan untuk memahami kejadian yang tampak biasa, namun menyimpan struktur logis yang dalam. Dari birthday paradox hingga prinsip inklusi-eksklusi, dan dari teori hingga aplikasi kriptografi dan pasar, kuliah ini mengajarkan kita untuk tidak hanya mencari satu penyebab, tetapi berpikir secara sistemik tentang **kombinasi kejadian** yang mendorong hasil.
