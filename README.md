# Tapscend (Android)

Tek dokunuşla tırmanış oyunu. Oyun `www/index.html` içinde; Capacitor onu bir Android uygulamasına sarıyor.

## APK almanın iki yolu

### A) Bilgisayara hiçbir şey kurmadan (GitHub)
1. github.com'da yeni, boş bir depo açın (özel olabilir).
2. Bu klasörün içeriğini depoya yükleyin (`main` dalına).
3. Deponun **Actions** sekmesinde "Android APK" işi kendiliğinden çalışır (5-10 dk).
4. İş bitince sayfanın altındaki **Artifacts** bölümünden `tapscend-debug-apk` dosyasını indirin, zip'i açın.
5. `app-debug.apk` dosyasını telefona atıp kurun (telefon "bilinmeyen kaynak" izni ister).

### B) Android Studio ile
1. Node.js 22+ ve Android Studio kurun.
2. Bu klasörde: `npm install` sonra `npx cap sync android`
3. `npx cap open android` ile projeyi Android Studio'da açın, Run'a basın.

## Oyunu değiştirince
`www/index.html` dosyasını değiştirin, sonra `npx cap sync android` (A yolunda depoya yüklemeniz yeterli).

## Mağazaya çıkmadan önce yapılacaklar
- **Reklamlar hâlâ demo.** Oyundaki "Reklam (demo)" ekranı 3 saniye bekletir, gerçek reklam göstermez ve para kazandırmaz. Gerçek reklam için AdMob hesabı ve reklam kimlikleri gerekir.
- **Paket adı:** `com.tapscend.game`. Yayından sonra değiştirilemez; kendi alan adınız varsa şimdi değiştirin (`capacitor.config.json` ve `android/app/build.gradle`).
- **İmzalı sürüm:** Mağaza debug APK kabul etmez; imzalı AAB gerekir (Android Studio > Build > Generate Signed App Bundle). İmza anahtarını kaybetmeyin.
- **Google Play geliştirici hesabı** (tek seferlik 25 $) ve mağaza sayfası: açıklama, ekran görüntüleri, gizlilik politikası bağlantısı, içerik derecelendirme anketi.
- Mağaza simgesi: `assets/play-store-icon-512.png`.
- Sürüm yükseltme: `android/app/build.gradle` içindeki `versionCode` her yüklemede artmalı.
