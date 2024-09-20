Bu proje, zaman serisi tahmini (time series forecasting) üzerine kuruludur. Özel olarak, havayolu yolcu sayısı tahmini yapmayı amaçlayan bir projedir. İşte bu projede yapılan ana adımlar:

1. **İş Problemi Tanımı:**
   - **Mont**: Tarih (aylık olarak).
   - **Passengers**: Aylık yolcu sayısı.

2. **Veriyi Anlamak ve Hazırlamak:**
   - Veriyi yükleyip ve inceleyerek `Month` ve `Passengers` sütunlarına odaklanılır.
   - Tarihleri datetime formatına çevirir ve `Month` sütununu indeks olarak ayarlar.
   - Verileri normalize etmek için `MinMaxScaler` kullanılır.

3. **Modelleme:**
   - Veriler, `SimpleRNN` gibi bir Recurrent Neural Network (RNN) modeli kullanılarak eğitilir.
   - Model, geçmiş verilerden öğrenerek gelecekteki yolcu sayılarını tahmin etmeye çalışır.

4. **Modelin Değerlendirilmesi:**
   - Eğitim ve test veri setleri üzerindeki performans değerlendirilir.
   - Modelin doğruluğunu ölçmek için `RMSE` (Root Mean Squared Error) kullanılır.

5. **Sonuçların Görselleştirilmesi:**
   - Eğitim sürecindeki kayıplar (loss) ve doğrulama kayıpları grafiğe dökülür.
   - Gerçek ve tahmin edilen değerler arasındaki farklar görselleştirilir.

### Kodda Yapılanlar:

- **Veri Ön İşleme:** Veriler normalize edilip, eğitim ve test setlerine ayrılır.
- **Model Eğitimi:** `SimpleRNN` modelini eğitmek için `fit` fonksiyonu kullanılır ve `EarlyStopping` ile `ModelCheckpoint` callback'leri uygulanır.
- **Sonuçların Yorumlanması:** Tahminler, ölçek dönüşümü yapılarak orijinal formata döndürülür ve `RMSE` hesaplanır.

Bu proje, havayolu yolcu sayısındaki mevsimsel ve trendsel değişiklikleri modellemek için zaman serisi analiz yöntemlerini kullanır ve derin öğrenme teknikleri ile tahmin yapar.