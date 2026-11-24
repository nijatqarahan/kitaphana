# Kitapxana - APK yapma rehberi (çevrimdışı çalışır)

Bu klasör hazır bir Capacitor projesidir. `www/` içindeki her şey (kitaplar, font,
PDF okuyucu, ZIP okuyucu) uygulamanın içine gömülür. APK kurulunca internet
olmadan çalışır.

## Yol A: Bilgisayarda Android Studio ile (en sağlam)

1. Node.js 20 veya üstünü kur (nodejs.org, LTS).
2. Android Studio'yu kur (developer.android.com/studio). İlk açılışta
   "Android SDK" kurulumunu tamamla.
3. Bu klasörü bilgisayara çıkar. Klasörün içinde terminal aç:
       npm install
       npx cap add android
       npx cap sync android
       npx cap open android
4. Android Studio açılınca Gradle indirmesi bitsin (alttaki ilerleme çubuğu).
5. Menü: Build > Build Bundle(s) / APK(s) > Build APK(s).
6. Bitince sağ altta "locate" bağlantısına bas. Dosya burada:
       android/app/build/outputs/apk/debug/app-debug.apk
7. APK'yı telefona/tablete gönder, aç, "bilinmeyen kaynaklardan kurulum"a izin ver.

## Yol B: Bilgisayarsız, GitHub ile (tarayıcıdan)

1. github.com'da ücretsiz hesap aç, yeni PRIVATE (özel) bir depo oluştur.
2. Bu klasörün içeriğini (www, package.json, capacitor.config.json,
   .github) depoya yükle ("Add file > Upload files").
3. Depoda "Actions" sekmesi > "Build APK" > "Run workflow".
4. 5-10 dakika sonra bitince çalışmanın içindeki "kitapxana-apk" dosyasını indir.
   Zip'in içinde app-debug.apk var.

## İmzalı (yayına hazır) APK

Debug APK telefonda sorunsuz çalışır. Başkalarıyla paylaşacaksan Android Studio'da
Build > Generate Signed Bundle / APK ile kendi anahtarını (keystore) oluşturup
imzala. Anahtarı ve şifresini sakla; sonraki güncellemeler aynı anahtarla
yapılmalı.

## Notlar

- Uygulama boyutu yaklaşık 20-25 MB olur.
- Özet ve sınav özelliği Claude'a bağlı çalışır; APK içinde çalışmaz
  (uygulama bunu söyleyen bir mesaj gösterir). Diğer her şey çevrimdışı çalışır.
- Eklediğin kitaplar, favoriler, yer imleri ve renk ayarları cihazda saklanır.
  Uygulama verisi silinirse (Ayarlar > Uygulamalar > Depolama > Verileri sil) gider.
- Kitapların telif hakkı sahiplerine aittir. APK'yı herkese açık yaymadan önce
  izinleri kontrol et.
- iPhone: bu proje Android içindir. iOS uygulaması için Mac, Xcode ve Apple
  Developer hesabı (yıllık ücretli) gerekir.
