# **Story Proofs & Axioms of Probability**

*Based on Statistics 110 by Prof. Joe Blitzstein – Harvard University*

---

## **Pendahuluan**

Topik kuliah ini memperkenalkan dua hal mendasar dalam probabilitas:

1. **Story Proofs** – metode pembuktian yang intuitif melalui logika cerita
2. **Aksioma Probabilitas** – fondasi logis dari semua teori probabilitas modern

Kuliah ini mengajak kita berpikir bukan sekadar dengan rumus, tapi dengan memahami logika di balik setiap aturan.

---

## **1. Apa Itu Story Proof?**

Story proof adalah cara membuktikan suatu rumus probabilitas atau kombinatorial dengan menceritakan ulang situasi nyata yang relevan. Pendekatan ini tidak mengandalkan aljabar berat, melainkan logika dan imajinasi.

Tujuan utama story proof:

* Membantu memahami “mengapa” suatu rumus benar
* Membangun intuisi kombinatorik
* Menjadikan matematika lebih manusiawi dan mudah diakses

### Contoh: **Identitas Vandermonde**

Rumus:

$$
\binom{n + m}{k} = \sum_{i = 0}^{k} \binom{n}{i} \cdot \binom{m}{k - i}
$$

**Cerita di baliknya:**

Misalnya ada dua kelas:

* Kelas A: n siswa
* Kelas B: m siswa
  Kita ingin memilih **k orang** dari gabungan dua kelas tersebut.

**Cara 1 (langsung):** Pilih k dari (n + m) siswa langsung → $\binom{n + m}{k}$

**Cara 2 (story):** Bagi pengambilan:

* Ambil i orang dari kelas A → $\binom{n}{i}$
* Ambil sisanya (k - i) dari kelas B → $\binom{m}{k - i}$
* Jumlahkan semua kombinasi dari i = 0 sampai k

Contoh numerik:

* n = 3, m = 2, k = 2
* Maka:

$$
\binom{5}{2} = 10 = \binom{3}{0}\binom{2}{2} + \binom{3}{1}\binom{2}{1} + \binom{3}{2}\binom{2}{0} = 1 + 6 + 3
$$

Kedua pendekatan menghitung hal yang sama: jumlah cara memilih k siswa dari dua kelas. Maka identitas ini terbukti benar secara intuitif.

---

## **2. Aksioma Probabilitas**

Aksioma adalah aturan dasar yang mendefinisikan bagaimana probabilitas bekerja. Tanpa aksioma, teori probabilitas akan menjadi kontradiktif dan tidak stabil.

### Aksioma 1: **Non-negativitas**

$$
P(A) \geq 0
$$

Probabilitas tidak mungkin negatif. Secara logika, tidak ada kejadian yang bisa memiliki peluang di bawah nol.

### Aksioma 2: **Normalisasi**

$$
P(S) = 1
$$

Total probabilitas dari semua kemungkinan dalam ruang sampel adalah 1. Kita yakin bahwa **sesuatu pasti terjadi**, entah A, B, atau lainnya.

### Aksioma 3: **Adisitivitas (untuk kejadian tak tumpang tindih)**

$$
P(A \cup B) = P(A) + P(B), \text{ jika } A \cap B = \emptyset
$$

Jika A dan B tidak bisa terjadi bersamaan, maka peluang gabungan A dan B adalah jumlah keduanya.

---

## **3. Konsekuensi dari Aksioma**

Dari tiga aksioma di atas, kita bisa menurunkan berbagai rumus penting:

### a. Penjumlahan Umum

Untuk A dan B yang bisa terjadi bersamaan:

$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

Rumus ini mengoreksi penjumlahan ganda dari area yang tumpang tindih.

### b. Komplemen

$$
P(A^c) = 1 - P(A)
$$

Jika peluang A terjadi adalah 0.3, maka peluang A tidak terjadi otomatis 0.7.

### c. Monotonisitas

$$
\text{Jika } A \subseteq B, \text{ maka } P(A) \leq P(B)
$$

Jika A adalah bagian dari B, maka peluang A terjadi pasti lebih kecil atau sama dengan peluang B.

### d. Probabilitas Kosong

$$
P(\emptyset) = 0
$$

Probabilitas dari kejadian yang **tidak mungkin terjadi sama sekali** adalah nol. Misalnya, hasil lemparan dadu bernilai 8 dari dadu 6 sisi.

---

## **4. Penjelasan Notasi dalam Probabilitas**

| Notasi      | Makna                                  |
| ----------- | -------------------------------------- |
| $\cup$      | Union → A atau B (gabungan)            |
| $\cap$      | Intersection → A dan B (perpotongan)   |
| $A^c$       | Komplemen A (kejadian A tidak terjadi) |
| $\emptyset$ | Himpunan kosong (kejadian mustahil)    |

---

## **5. Penutup**

Story proof mengajarkan kita bahwa rumus matematika sering kali bisa dibuktikan secara intuitif jika kita mengerti konteks dan bisa menjelaskannya dengan cerita.
Sementara itu, aksioma probabilitas memberi kita kerangka logis untuk semua rumus dan perhitungan yang akan digunakan dalam teori peluang dan statistik.
