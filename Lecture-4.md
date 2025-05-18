# **Lecture 4: Disjoint and Independent Events**

Based on Statistics 110 by Prof. Joe Blitzstein – Harvard University

---

## **Pendahuluan**

Dalam kuliah ini, kita mendalami dua konsep mendasar dalam probabilitas: **kejadian yang saling lepas (disjoint events)** dan **kejadian yang saling bebas (independent events)**. Keduanya sering terdengar mirip secara bahasa, tetapi secara matematis dan konseptual sangat berbeda. Kuliah ini juga memperkenalkan prinsip dasar conditional probability dan aturan perkalian (multiplication rule), serta aplikasi penting melalui *Newton–Pepys Problem* yang menggunakan distribusi binomial sebagai ilustrasi konkret.

---

## **1. Disjoint Events (Kejadian Saling Lepas)**

### **Definisi**

Dua kejadian A dan B dikatakan **saling lepas** jika tidak mungkin terjadi secara bersamaan. Secara formal:

$$
A \cap B = \emptyset \quad \text{maka} \quad P(A \cap B) = 0
$$

### **Contoh**

Melempar sebuah dadu:

* A = mendapatkan angka 2
* B = mendapatkan angka 5

Karena satu lemparan hanya menghasilkan satu angka, maka A dan B tidak bisa terjadi bersamaan. Artinya, A dan B saling lepas.

### **Rumus Gabungan untuk Kejadian Saling Lepas**

$$
P(A \cup B) = P(A) + P(B)
$$

Rumus ini berlaku hanya jika A dan B disjoint.

---

## **2. Independent Events (Kejadian Saling Bebas)**

### **Definisi**

Dua kejadian A dan B dikatakan **saling bebas** jika terjadinya A tidak mempengaruhi probabilitas terjadinya B, dan sebaliknya.

$$
P(A \cap B) = P(A) \cdot P(B)
$$

### **Contoh**

Melempar dua koin:

* A = koin pertama menunjukkan kepala
* B = koin kedua menunjukkan kepala

Kedua kejadian ini tidak mempengaruhi satu sama lain, maka A dan B adalah kejadian independen.

---

## **3. Disjoint vs Independent: Perbedaan Mendasar**

| Konsep                  | Disjoint (Saling Lepas)                   | Independent (Saling Bebas)                    |
| ----------------------- | ----------------------------------------- | --------------------------------------------- |
| Bisa terjadi bersamaan? | Tidak bisa terjadi bersama                | Bisa terjadi bersama                          |
| Interseksi              | $P(A \cap B) = 0$                         | $P(A \cap B) = P(A) \cdot P(B)$               |
| Makna logis             | Tidak ada overlap antara A dan B          | Tidak ada pengaruh antara A dan B             |
| Contoh                  | 1 lemparan dadu: A = angka 3, B = angka 6 | 2 lemparan koin: kepala di masing-masing koin |

Catatan penting: **Jika dua kejadian disjoint dan memiliki probabilitas non-zero, maka mereka tidak bisa independen.** Karena jika $P(A \cap B) = 0$ tapi $P(A) \cdot P(B) > 0$, maka mereka tidak setara.

---

## **4. Conditional Probability**

### **Definisi**

Probabilitas suatu kejadian A terjadi **dengan syarat** kejadian B telah terjadi.

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)} \quad \text{dengan syarat } P(B) > 0
$$

### **Makna Konseptual**

Conditional probability membatasi ruang sampel kita hanya pada kejadian B. Kemudian kita menghitung berapa besar proporsi dari B yang juga memenuhi A.

---

## **5. Aturan Perkalian (Multiplication Rule)**

Diturunkan langsung dari conditional probability:

$$
P(A \cap B) = P(A) \cdot P(B \mid A)
$$

Jika A dan B **independen**, maka:

$$
P(A \cap B) = P(A) \cdot P(B)
$$

---

## **6. Newton–Pepys Problem dan Distribusi Binomial**

### **Masalah**

Samuel Pepys bertanya kepada Isaac Newton: dari tiga skenario melempar dadu berikut, mana yang memiliki peluang tertinggi?

1. Melempar 6 dadu dan mendapatkan **minimal 1 angka enam**
2. Melempar 12 dadu dan mendapatkan **minimal 2 angka enam**
3. Melempar 18 dadu dan mendapatkan **minimal 3 angka enam**

### **Distribusi Binomial**

Distribusi binomial menjawab pertanyaan:
"Berapa besar kemungkinan sebuah kejadian sukses terjadi sebanyak k kali dari n percobaan, jika peluang sukses tiap percobaan adalah p?"

Karena ini adalah percobaan independen dengan dua hasil (muncul angka 6 = sukses, tidak muncul = gagal), kita menggunakan distribusi binomial:

$$
P(X = k) = \binom{n}{k} \cdot p^k \cdot (1 - p)^{n - k}
$$

Dengan:

* $n$ = jumlah percobaan (jumlah dadu)
* $k$ = jumlah keberhasilan (angka 6 yang muncul)
* $p = \frac{1}{6}$ = peluang muncul angka 6

---

### **Tujuan: Mencari Peluang P(X ≥ k)**

Lebih mudah dihitung menggunakan komplemen:

$$
P(X \geq k) = 1 - \sum_{i=0}^{k-1} P(X = i)
$$

---

### **Perhitungan Manual**

#### **Skenario 1: 6 dadu, minimal 1 enam**

$$
P(X \geq 1) = 1 - P(X = 0) = 1 - \left( \frac{5}{6} \right)^6 \approx 0.6651
$$

#### **Skenario 2: 12 dadu, minimal 2 enam**

$$
P(X \geq 2) = 1 - P(X = 0) - P(X = 1)
$$

$$
P(X = 0) = \left( \frac{5}{6} \right)^{12} \approx 0.112
$$

$$
P(X = 1) = \binom{12}{1} \cdot \frac{1}{6} \cdot \left( \frac{5}{6} \right)^{11} \approx 0.323
$$

$$
P(X \geq 2) \approx 1 - 0.112 - 0.323 = 0.565
$$

#### **Skenario 3: 18 dadu, minimal 3 enam**

$$
P(X \geq 3) = 1 - P(X = 0) - P(X = 1) - P(X = 2)
$$

Hasil totalnya kira-kira:

$$
P(X \geq 3) \approx 0.273
$$

---

### **Kesimpulan Newton–Pepys**

| Skenario                | Peluang                |
| ----------------------- | ---------------------- |
| A: ≥1 enam dari 6 dadu  | **0.6651** ✅ tertinggi |
| B: ≥2 enam dari 12 dadu | 0.565                  |
| C: ≥3 enam dari 18 dadu | 0.273                  |

Meskipun ketiganya memiliki **ekspektasi** hasil 1, 2, dan 3 angka enam masing-masing, **peluang aktual keberhasilan menurun**. Mengapa? Karena distribusi binomial menyebar, dan saat target keberhasilan meningkat, jumlah peluang yang mendukung target itu semakin kecil.

---

## **Penutup**

Lecture 4 mengajarkan perbedaan mendalam antara kejadian saling lepas dan kejadian saling bebas. Dalam praktiknya, kita perlu hati-hati dalam membedakan keduanya karena mereka menghasilkan perhitungan yang berbeda secara fundamental. Kita juga belajar bagaimana probabilitas bersyarat dan aturan perkalian digunakan untuk memodelkan kejadian-kejadian kompleks. Newton–Pepys Problem menunjukkan bahwa intuisi kita tidak selalu akurat dalam menilai probabilitas, dan distribusi binomial memberikan alat yang tepat untuk menjawab pertanyaan semacam ini.
