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

