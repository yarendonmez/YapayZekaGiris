![image](https://github.com/user-attachments/assets/885f9af9-af41-488b-82c3-a2df44a69856)
![image](https://github.com/user-attachments/assets/8f68aaf7-e856-4fe2-953a-8dd48a08d7b7)


## 🌟 Örnek: Arad'dan Bükreş'e Greedy Arama Adımları

### 🔍 Hatırla: Greedy Search ne yapıyordu?

Sadece **h(n)** değerine, yani “hedefe olan tahmini uzaklığa” bakıyor.
Yani:

* Her adımda **en küçük h(n)** değerine sahip düğüm seçilir.
* Gerçek mesafeler (g(n)) = yani yolların uzunluğu **dikkate alınmaz.**

---

### 🧭 Grafik ve Tablo Nereden Geliyor?

* Grafikteki sayılar: **kuş uçuşu mesafeler** (h(n)), yani **Bükreş'e olan tahmini düz mesafe**.
* Örnek tablo: sağdaki “Straight-line distance to Bucharest”.

---

## 🚀 Adım Adım Greedy Seçimleri:

### ✅ 1. Başlangıç: **Arad**

* Arad’ın komşuları:

  * Sibiu → h = 253
  * Timisoara → h = 329
  * Zerind → h = 374
* ✅ En küçük h(n): **Sibiu (253)**
* **Seçim**: Arad → Sibiu

---

### ✅ 2. Nokta: **Sibiu**

* Sibiu’nun komşuları:

  * Fagaras → h = 176
  * Rimnicu Vilcea → h = 193
  * Oradea → h = 380 (zaten geri gitmek)
* ✅ En küçük h(n): **Fagaras (176)**
* **Seçim**: Sibiu → Fagaras

---

### ✅ 3. Nokta: **Fagaras**

* Fagaras’ın komşusu:

  * Bucharest → h = 0
* ✅ En küçük h(n): **Bucharest**
* **Seçim**: Fagaras → Bucharest

---

## 💡 Final Yol:

```
Arad → Sibiu → Fagaras → Bucharest
```

---

### 🧠 Ama… Gerçek Maliyet Ne Olur?

Eğer yol uzunluklarına (g(n)) baksaydık:

* Arad → Sibiu = 140
* Sibiu → Fagaras = 99
* Fagaras → Bucharest = 211
  Toplam: **450 birimlik yol**

Ama başka yollar olabilir mesela:

> Arad → Timisoara → Lugoj → Mehadia → Dobreta → Craiova → Pitesti → Bucharest
> Bu yol daha kısa olabilir ama h(n) değerleri daha yüksek diye Greedy **bakmaz bile!**

---

## ❗ Kafa Karışıklığı Neden Oluyor?

| Harita üzerindeki yol üstündeki rakamlar | Gerçek yol uzunlukları (g(n)) |
| ---------------------------------------- | ----------------------------- |
| Sağdaki listede görünen sayılar          | Kuş uçuşu tahminleri (h(n))   |

> Greedy Search **sadece** h(n) ile ilgilenir, yani sağdaki listedeki değerlerle.
> Yani:

* Yol üzerindeki mesafeleri **yok sayar**,
* “Bana hedefe en yakın gözüken yer neresi?” diye sorar.

---

---

## 🧠 **Açgözlü Arama – Özellikler**

---

### ✅ **1. Completeness (Tamlık): HAYIR**

> Bir algoritma complete ise, **çözüm varsa kesinlikle bulur**.

* Greedy bunu garanti etmez çünkü **yalnızca tahmini en kısa yola odaklanır.**
* Eğer **döngüye girerse veya yanlış yola saparsa**, hedefe ulaşamayabilir.

📌 **Slayttaki örnek:**

* Iasi → Neamt → Iasi → Neamt…
* Sonsuz döngüye girebilir, çünkü `h(n)` hep aynı yerlere daha yakın gözükebilir.

---

### ⏳ **2. Time Complexity: O(b^m)**

> b = dallanma faktörü (bir düğümün kaç çocuğu var)
> m = ağacın maksimum derinliği

* En kötü durumda her dalı denemesi gerekebilir → **exponential zaman**.
* **Ama!** Eğer `h(n)` çok iyi tasarlanmışsa (örneğin gerçek mesafeye çok yakınsa), bu süre **çok azalabilir**.
* Yani: **Heuristic fonksiyonu ne kadar iyi → zaman o kadar kısa.**

---

### 💾 **3. Space Complexity: O(b^m)**

> Bellek karmaşıklığı

* Çünkü **bütün aday düğümleri bellekte tutar**, hepsini karşılaştırmak ister (priority queue).
* Bu yüzden Greedy arama bellekte çok yer kaplayabilir.

---

### ❌ **4. Optimality (En iyi çözüm bulma): HAYIR**

* En kısa veya en ucuz yolu garanti etmez.
* Sadece “hedefe en yakın gibi görünen yere” gider.
* Gerçek maliyetleri (g(n)) **hiç umursamaz.**

🧠 Örnek:

* A → B → C → Hedef yolunun toplam maliyeti 100
* Ama A → Z → Hedef yolu kuş uçuşu kısa görünür ama **maliyeti 300’dür**
  → Greedy 300’lük yolu seçer.

---

### 🔍 Not:

> Bu özellikler aslında bize şunu söyler:

* Greedy Search **çok hızlı olabilir ama kördür.**
* “Acele işe şeytan karışır” algoritmasıdır 😅

---


