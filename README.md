# YOLO ile Eş Zamanlı Çatlak ve Bina Durumu Tespiti  

Bu proje, **Ultralytics YOLO** modelleri kullanarak aynı anda iki farklı nesne tespit modelini (çatlak tespiti ve bina durumu tespiti) tek bir video kaynağı üzerinden çalıştırır.  

## 🚀 Özellikler
- Aynı anda iki YOLO modeli çalıştırma
- Çoklu iş parçacığı (threading) desteği
- Canlı kamera/harici video kaynağından görüntü alma
- Çıktıları ayrı pencerelerde gösterme

## 📦 Gereksinimler
Projeyi çalıştırmadan önce aşağıdaki kütüphaneleri kurmalısınız:

```bash
pip install ultralytics opencv-python
🔧 Kullanım
Eğitimli YOLO modellerinizi (catlak.pt ve bina.pt) proje dizinine koyun.

Python dosyasını çalıştırın:

bash
Kodu kopyala
python main.py
İki farklı pencere açılacaktır:

catlak Tespiti → Çatlak tespit sonuçlarını gösterir

Bina durumu → Bina durumunu tespit eden modelin çıktısını gösterir

Uygulamadan çıkmak için q tuşuna basın.

📂 Proje Yapısı
bash
Kodu kopyala
├── main.py          # Ana Python dosyası
├── catlak.pt        # Çatlak tespit modeli (YOLO)
├── bina.pt          # Bina durumu tespit modeli (YOLO)
└── README.md        # Proje açıklaması
🖼️ Görselleştirme
Model tespit ettiği nesneleri dikdörtgen kutular ve etiketler ile çizer.

Kutular pembe renkte ((255, 0, 102)) çizilir.

⚙️ Video Kaynağı
Kodda kamera kaynağı şu şekilde ayarlanmıştır:

python
Kodu kopyala
video_thread = VideoCaptureThread(2)
0 → Varsayılan bilgisayar kamerası

1 → Harici kamera

2 → Başka bir video kaynağı

Kendi sisteminize göre değiştirebilirsiniz.

📝 Notlar
conf parametresi ile tahmin güven seviyesi ayarlanabilir:

Çatlak modeli: conf=0.6

Bina modeli: conf=0.4

Aynı frame üzerinde iki model eş zamanlı çalıştırılır.
