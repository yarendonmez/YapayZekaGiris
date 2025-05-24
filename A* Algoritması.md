
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


