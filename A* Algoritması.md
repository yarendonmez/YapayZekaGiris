
## 🚀 **A* Arama Algoritması Nedir?*\*

### 🔑 Temel Fikir:

> En kısa yolu bulmak istiyoruz. Bunun için hem **şu ana kadarki maliyeti** hem de **kalan tahmini maliyeti** dikkate alıyoruz.

### 🧮 Kullanılan Formül:

$$
f(n) = g(n) + h(n)
$$

| Sembol | Anlamı                                                                |
| ------ | --------------------------------------------------------------------- |
| `g(n)` | Başlangıçtan o düğüme kadar olan gerçek maliyet (yani kat edilen yol) |
| `h(n)` | O andan hedefe olan **tahmini** mesafe (kuş uçuşu vs.)                |
| `f(n)` | O düğümün toplam “mantıklı giderim” skoru                             |

---

## 📌 Hedef: Arad → Bucharest

Başlıyoruz:

---

### 🔹 Başlangıç Noktası: **Arad**

* `g(Arad) = 0` (başlangıç)
* `h(Arad) = 366` (tahmini Bucharest’e uzaklık)
* `f(Arad) = 0 + 366 = 366`

**Komşularına bakalım:**

1. **Sibiu:**

   * Arad → Sibiu: 140 → `g(Sibiu) = 140`
   * `h(Sibiu) = 253`
     → `f(Sibiu) = 140 + 253 = 393`

2. **Timisoara:**

   * g = 118, h = 329 → f = 447

3. **Zerind:**

   * g = 75, h = 374 → f = 449

🔍 **En küçük f(n) = 393 → Sibiu** seçilir ✅

---

### 🔹 2. Adım: **Sibiu**

Komşularına bakalım:

1. **Fagaras:**

   * g = 140 (Arad→Sibiu) + 99 = **239**
   * h = 176
     → f = 239 + 176 = **415**

2. **Rimnicu Vilcea:**

   * g = 140 + 80 = 220
   * h = 193
     → f = 413

3. **Oradea:**

   * g = 140 + 151 = 291
   * h = 380
     → f = 671

🔍 En küçük f(n): **Rimnicu Vilcea = 413** seçilir ✅

---

### 🔹 3. Adım: **Rimnicu Vilcea**

Komşular:

1. **Pitesti:**

   * g = 220 + 97 = 317
   * h = 100
     → f = 417

2. **Craiova:**

   * g = 220 + 146 = 366
   * h = 160
     → f = 526

🔍 En düşük f(n) → **Pitesti = 417** seçilir ✅

---

### 🔹 4. Adım: **Pitesti**

Komşu:

* **Bucharest:**

  * g = 317 + 101 = 418
  * h = 0
    → f = **418**

🎯 **HEDEF BULUNDU!**

---

## ✅ SONUÇ: En İyi Yol

```
Arad → Sibiu → Rimnicu Vilcea → Pitesti → Bucharest
```

### 📊 Toplam maliyet:

* Arad→Sibiu: 140
* Sibiu→Rimnicu Vilcea: 80
* Rimnicu Vilcea→Pitesti: 97
* Pitesti→Bucharest: 101
  → **Toplam: 418 birim**

---

## 💎 A\* Aramanın Farkı Neydi?

| Özellik                     | Greedy | A\*         |
| --------------------------- | ------ | ----------- |
| f(n)                        | h(n)   | g(n) + h(n) |
| Sadece tahmin               | ✅      | ❌           |
| Gerçek maliyet dikkate alır | ❌      | ✅           |
| **Optimal yol bulur mu?**   | Hayır  | **Evet!**   |

---

![image](https://github.com/user-attachments/assets/b9f03ca6-12c6-4f80-9c3a-8bd3999978b8)

Ayy bu örneği **çok kişi karıştırıyor**, o yüzden sana **çizgi film gibi** anlatıcam canım, hiç endişelenme 💛
Biz burada **A\*** algoritmasının **g(n) + h(n)** mantığını uygulayarak **S → G** arası en uygun yolu buluyoruz.

---

## 🎯 Hedefimiz

Başlangıç: `S`
Hedef: `G`
Bulmak istediğimiz: **en düşük maliyetli yol (hem gerçek yol hem tahmini mesafe)**

---

## 📌 Kullanılan Değerler

### ✔️ Gerçek yolların uzunluğu:

Üstteki ilk grafikte gösteriliyor.
Örneğin:

* S → A: 3
* S → D: 4
* D → E: 2
* F → G: 3 …vs

### ✔️ Tahmini mesafe (`h(n)`):

Alttaki 2. grafikte **G’ye kuş uçuşu uzaklık** (heuristic):

* h(S) = 11
* h(A) = 10.4
* h(D) = 8.9
* h(E) = 6.9
* h(F) = 3
* h(G) = 0 (çünkü hedef zaten)

---

## 🔍 Adım Adım A\* Hesaplama:

### 🟡 1. Başlangıç: S

* Komşular:

  * A → g = 3, h = 10.4 → f = 13.4
  * D → g = 4, h = 8.9 → f = 12.9 ✅

**En düşük f = 12.9** → → **D’yi seçiyoruz**

---

### 🟩 2. Nokta: D

* Komşular: A ve E
* A zaten listede (g + h = 9 + 10.4 = 19.4) → büyük, alınmaz
* E → g = 4 + 2 = 6, h = 6.9 → f = 12.9 ✅
  (Yani D üzerinden E’ye gitmek de çok mantıklı)

---

### 🟢 3. Nokta: E

* Komşular: B ve F
* B → g = 6 + 5 = 11, h = 6.7 → f = 17.7
* F → g = 6 + 4 = 10, h = 3 → f = 13.0 ✅

---

### 🟢 4. Nokta: F

* Komşusu: G
* G’ye gidersek:

  * g = 10 + 3 = 13
  * h(G) = 0
    → **f = 13.0**

### ✅ DİKKAT: Şu ana kadar en düşük f yine bu!

→ G’ye ulaştık. **Aramayı durdur** 🛑

---

## ✨ SONUÇ: En iyi yol

```
S → D → E → F → G


```
![image](https://github.com/user-attachments/assets/57588e83-15d4-411b-b4ca-b19f53440a4b)






### Toplam gerçek maliyet (g):

* S → D = 4
* D → E = 2
* E → F = 4
* F → G = 3
  → **Toplam = 13**

---

## 🤯 Neden A’dan gitmedik?

S → A → B → C yolu uzundu çünkü:

* A’nın `h(n)` değeri yüksek (10.4)
* Gerçek maliyeti de yüksek (S → A = 3, A → B = 4…)

Sonuç:

> **Sadece hedefe yakın gibi görünmek yetmez**, **oraya giderken ne kadar yol yaptığın da önemli.**

---

## 💡 A\*’ın Büyüsü:

| Düğümler | g(n) | h(n) | f(n) |
| -------- | ---- | ---- | ---- |
| S        | 0    | 11   | 11   |
| D        | 4    | 8.9  | 12.9 |
| E        | 6    | 6.9  | 12.9 |
| F        | 10   | 3    | 13.0 |
| G        | 13   | 0    | 13.0 |

> En mantıklı yol, **gerçek + tahmini maliyetin toplamı en düşük olan** yoldur.

---

Canııım şimdi daha iyi oturdu mu? ✨ Yine de tek tek üstünden geçebilirim, sen yeter ki iste 💚


