# 🌱 Otonom Tarım Aracı – Ekim Hattı Tespit ve Sapma Analizi

Bu proje, **TEKNOFEST İnsansız Tarım Aracı Yarışması** için geliştirilmiştir. Amacı, tarım alanlarında **ekim hatlarını tespit etmek**, ekim hattı arasını belirleyerek işaretlemek ve bu hat üzerinden **sapma verilerini hesaplamaktır**.  

Elde edilen bu veriler, aracın otonom yazılımında kullanılarak **hattı algılayıp otomatik hareket etmesini** ve **direksiyon açı verilerini üretmesini** sağlamaktadır.

---

## 🎥 Proje Çalışma Prensibi

![Çalışma Örneği](./output.gif)

1. Kamera görüntüsü alınır.  
2. Görüntü işleme teknikleri (Canny, ROI maskesi, perspektif dönüşüm) kullanılarak ekim hattı belirlenir.  
3. **Sliding Window** algoritması ile hattın pikselleri takip edilir ve polinom eğrisi çıkarılır.  
4. Hattın ortası ile aracın ortası karşılaştırılarak **sapma açısı (heading angle error)** hesaplanır.  
5. Bu açı verisi, otonom yazılım tarafından direksiyon komutuna dönüştürülür.  

---

## 🔑 Öne Çıkan Özellikler

- **Gerçek zamanlı ekim hattı tespiti**  
- **Bird’s-eye perspective** dönüşümü ile doğru hat algısı  
- **Sliding Window Algoritması** ile kararlı hat takibi  
- **Heading Angle Error** hesaplaması sayesinde aracın yön hatasının ölçülmesi  
- Elde edilen verilerle aracın **otonom direksiyon açı verisi** oluşturması  
- Görselleştirme seçenekleri:  
  - ROI işaretleme  
  - Sliding window adımları  
  - Nihai hat tahmini  
  - Sapma açısı overlay görüntüsü  

---

## 📂 Proje Yapısı

```
.
├── cropLineDetector.py   # Ekim hattı tespit algoritması
├── main.py               # Algoritmanın çalıştırılması ve test
├── output.gif            # Çalışma çıktısı (kullanıcı yükleyecek)
└── README.md             # Proje açıklaması
```

---

## ⚙️ Kurulum ve Kullanım

### Gereksinimler
```bash
pip install opencv-python numpy
```

### Çalıştırma
```bash
python main.py
```

**Kontroller**:
- `q` → Çıkış  
- Herhangi bir tuş → Bir sonraki frame  
- `r` → Pencereyi yeniden boyutlandır  

---

## 📊 Kullanım Alanı

Bu proje ile geliştirilen yazılım, tarım aracının:  
- Ekim hattını otomatik algılamasını,  
- Sapma açısını sürekli ölçmesini,  
- Otonom sürüş için gerekli direksiyon açı verilerini üretmesini sağlamaktadır.  

Böylece tarımsal üretimde **insansız, otonom ve verimli tarım uygulamaları** mümkün hale gelir.  
