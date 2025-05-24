
## 📌 **Bilgili Arama Stratejileri Genel Bakış**

> Bu stratejiler **probleme dair ek bilgi** ile çalışır. Hepsi birer “Best-First Search” (en iyi görüneni seç) türevidir. Temelinde her durumda bir **öncelik değeri (f(n))** vardır.

### 1. **En İyi Öncelikli Arama (Best-First Search)**

* Genel fikir: Her düğüm için **"ne kadar cazip"** olduğunu hesaplayan bir `f(n)` fonksiyonu vardır.
* **En cazip olan** düğüm seçilir ve genişletilir.
* Bu yüzden **Priority Queue (öncelik sırası kuyruğu)** kullanılır.

📍 `f(n)` → Düğümün değerlendirme puanı. Sezgisel olabilir veya maliyeti içerebilir.

---

### ⚡️ Best-First’in 2 Özel Durumu

---

### 2. **Açgözlü Arama (Greedy Search)**

* Tahmin fonksiyonu: `f(n) = h(n)`
* Sadece **hedefe olan tahmini uzaklığı** dikkate alır.
* Hızlıdır ama bazen **kestirme ama kötü yollar** seçer.
* Optimal değildir, en kısa yolu her zaman bulmaz.

---

### 3. **A* Arama (A-Star)*\* ⭐️

* En bilinen ve güçlü bilgili arama algoritmasıdır.
* `f(n) = g(n) + h(n)`

  * `g(n)`: Başlangıçtan o düğüme kadar olan gerçek maliyet.
  * `h(n)`: O düğümden hedefe olan tahmini maliyet (heuristic).
* A\*, **hem hızlı hem de optimal** sonuçlar verir *eğer h(n) sezgiseli düzgünse*.

---

### 4. **IDA* (Iterative Deepening A*)\*\*

* A\*’ın belleğe dost hali.
* **A*’ı derinlik sınırlı şekilde*\* tekrar tekrar çalıştırır.
* Bellek problemi yaşamadan A\* kalitesinde sonuç verir.
* Zaman açısından biraz pahalı ama bellek tasarrufludur.

---

### 5. **SMA* (Simplified Memory-Bounded A*)\*\*

* Belleği sınırlı sistemler için geliştirilmiş A\* türevidir.
* **Yetersiz RAM/alan varsa**, en az gerekli düğümleri tutar, kalanları siler (gerektiğinde tekrar oluşturur).
* Zekice ama daha yavaş olabilir.

---

🧠 Kıyaslamak gerekirse:

| Algoritma | Optimal mi? | Bellek kullanımı | Hız        |
| --------- | ----------- | ---------------- | ---------- |
| Greedy    | ❌           | Az               | Çok hızlı  |
| A\*       | ✅           | Yüksek           | Orta       |
| IDA\*     | ✅           | Az               | Orta/yavaş |
| SMA\*     | ✅           | Kısıtlı          | Daha yavaş |

---

Hazırsan şimdi sıradaki slaytı gönder canım 🤍 Bu tempo süper gidiyor, seninle çalışmak hep çok zevkli 😌
