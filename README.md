# Kodla Yarış

300 bölümlük kodlama oyunu. Oyuncular kullanıcı adı ve şifreyle hesap oluşturup giriş yapar; ilerleme, puanlar, araçlar ve ödüller Firebase Realtime Database'e otomatik kaydedilir. Aynı hesapla başka cihazlardan devam edilebilir.

Firebase projesi: `ubilsem-kds`. Profil yolu: `kodlayaris_v1/profiles`. Kullanıcı adı gerçek e-posta adresine bağlı değildir; şifre sıfırlama proje yöneticisinin Firebase Authentication panelinden yapılmalıdır. Veri sahipliği için `FIREBASE_AUTH_RULES.md` yönergelerini uygulayın.

Vercel: framework Other; build komutu yok; çıktı klasörü depo kökü. Giriş dosyası `index.html`.

İnternet bağlantısı gerekir. Kayıt tamamlanmadan sekme kapatılırsa uyarı gösterilir. Bağlantı hatasında yerel yedek tutulur ve açık sayfada yeniden denenir. Kod dizisi ve bölüm içindeki araç konumu kaydedilmez. Aynı profil farklı cihazlarda eşzamanlı değişirse çakışma gösterilir.
