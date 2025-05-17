# **Lecture 5: Conditioning Continued, Law of Total Probability**

Based on Statistics 110 by Prof. Joe Blitzstein – Harvard University

---

## **Pendahuluan**

Dalam kuliah ini, kita melanjutkan pembahasan tentang probabilitas bersyarat (*conditional probability*) dan memperkenalkan dua konsep penting: **Hukum Probabilitas Total** (*Law of Total Probability*) dan **Teorema Bayes** (*Bayes' Theorem*). Kedua konsep ini sangat berguna dalam menghitung probabilitas suatu kejadian berdasarkan informasi tambahan atau bukti baru.

---

## **1. Probabilitas Bersyarat (Conditional Probability)**

### **Definisi**

Probabilitas bersyarat adalah probabilitas suatu kejadian A terjadi dengan syarat bahwa kejadian B telah terjadi. Secara matematis:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)} \quad \text{dengan syarat } P(B) > 0
$$

### **Makna Konseptual**

Probabilitas bersyarat membatasi ruang sampel kita hanya pada kejadian B. Kemudian kita menghitung berapa besar proporsi dari B yang juga memenuhi A.

---

## **2. Hukum Probabilitas Total (Law of Total Probability)**

### **Definisi**

Jika $\{B_1, B_2, ..., B_n\}$ adalah partisi dari ruang sampel S (yaitu, kejadian-kejadian yang saling lepas dan mencakup seluruh ruang sampel), maka untuk setiap kejadian A:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i) \cdot P(B_i)
$$

### **Makna Konseptual**

Hukum ini memungkinkan kita menghitung probabilitas total dari A dengan mempertimbangkan semua cara A dapat terjadi melalui partisi-partisi B\_i.

---

## **3. Teorema Bayes (Bayes' Theorem)**

### **Definisi**

Teorema Bayes memungkinkan kita membalik arah kondisi dalam probabilitas bersyarat:

$$
P(B_i \mid A) = \frac{P(A \mid B_i) \cdot P(B_i)}{\sum_{j=1}^{n} P(A \mid B_j) \cdot P(B_j)}
$$

### **Makna Konseptual**

Teorema ini digunakan untuk memperbarui keyakinan kita tentang probabilitas suatu hipotesis B\_i berdasarkan bukti baru A.

---

## **4. Contoh Penerapan**

Misalkan sebuah tes medis memiliki sensitivitas 99% dan spesifisitas 95%. Jika 1% populasi memiliki penyakit tersebut, dan seseorang mendapatkan hasil tes positif, berapa probabilitas bahwa orang tersebut benar-benar memiliki penyakit?

### **Langkah-langkah:**

* P(D) = 0.01 (probabilitas memiliki penyakit)
* P(¬D) = 0.99 (probabilitas tidak memiliki penyakit)
* P(Positif | D) = 0.99 (sensitivitas)
* P(Positif | ¬D) = 0.05 (1 - spesifisitas)

### **Menggunakan Teorema Bayes:**

$$
P(D \mid \text{Positif}) = \frac{P(\text{Positif} \mid D) \cdot P(D)}{P(\text{Positif} \mid D) \cdot P(D) + P(\text{Positif} \mid \neg D) \cdot P(\neg D)} = \frac{0.99 \cdot 0.01}{0.99 \cdot 0.01 + 0.05 \cdot 0.99} \approx 0.167
$$

Jadi, meskipun tes tersebut sangat akurat, probabilitas bahwa seseorang benar-benar memiliki penyakit setelah hasil tes positif adalah sekitar 16.7%.

---

## **5. Kesimpulan**

Dalam kuliah ini, kita mempelajari bagaimana probabilitas bersyarat, hukum probabilitas total, dan teorema Bayes saling berkaitan dan digunakan untuk menghitung probabilitas kejadian berdasarkan informasi tambahan. Pemahaman konsep-konsep ini sangat penting dalam berbagai aplikasi, termasuk pengujian medis, deteksi penipuan, dan sistem rekomendasi.
