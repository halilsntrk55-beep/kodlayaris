# Kodla Yarış

300 bölümlük kodlama oyunu. Öğrenci adını ve soyadını yazarak Firebase profilini açar; bölümler, puanlar, araçlar ve ödüller otomatik kaydedilir.

Firebase projesi: `ubilsem-kds`. Kayıt yolu: `kodlayaris_v1/profiles`. İsimle giriş şifreli kimlik doğrulama değildir; aynı isim aynı profili açar.

Vercel: framework Other; build komutu yok; çıktı klasörü depo kökü. Giriş dosyası `index.html`.

İnternet bağlantısı gerekir. Kayıt tamamlanmadan sekme kapatılırsa uyarı gösterilir. Bağlantı hatasında yerel yedek tutulur ve açık sayfada yeniden denenir. Kod dizisi ve bölüm içindeki araç konumu kaydedilmez. Aynı profil farklı cihazlarda eşzamanlı değişirse çakışma gösterilir.
