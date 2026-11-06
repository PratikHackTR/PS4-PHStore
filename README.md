# PHStore PS4 — Modern Homebrew Game & Patch Store

[![PS4 Homebrew](https://img.shields.io/badge/PS4-Homebrew-blue.svg)](https://github.com/PratikHackTR)
[![GoldHEN Compatible](https://img.shields.io/badge/GoldHEN-5.05%20--%2011.00-gold.svg)](https://github.com/PratikHackTR)
[![QuickJS Native](https://img.shields.io/badge/Engine-QuickJS%20Native-brightgreen.svg)](https://github.com/PratikHackTR)
[![Latest Release](https://img.shields.io/badge/Release-v02.42-orange.svg)](https://github.com/PratikHackTR)

> [!NOTE]
> **Languages / Diller:** This documentation is provided in both **English** (first) and **Türkçe** (below).
> Jump to [Türkçe Kullanım ve Kurulum Kılavuzu](#tr-türkçe-kullanım-ve-kurulum-rehberi).

---

## 🇬🇧 English Documentation

### Table of Contents
1. [Overview & Features](#overview--features)
2. [Editions (Standard vs +TR)](#editions-standard-vs-tr)
3. [Installation Methods](#installation-methods)
   - [Method 1: USB Flash Drive / External HDD](#method-1-usb-flash-drive--external-hdd-recommended)
   - [Method 2: Mobile Phone or PC via FTP (FileZilla / AndroFTP)](#method-2-mobile-phone-or-pc-via-ftp-no-usb-required)
   - [Method 3: Direct Remote Package Installer (RPI)](#method-3-remote-package-installer-rpi)
4. [How-To: Phone Bridge & VikingFile Link Catcher](#how-to-phone-bridge--vikingfile-link-catcher)
   - [Video Tutorial](#video-tutorial)
   - [Manual Method (Quick & Easy)](#manual-method-quick--easy)
   - [Automatic Bookmarklet Method](#automatic-bookmarklet-method)
   - [Understanding Status Indicators](#understanding-status-indicators)
   - [Troubleshooting Link Capture](#troubleshooting-link-capture)
5. [Recommended Settings & Best Practices](#recommended-settings--best-practices)
6. [Credits & Social Links](#credits--social-links)

---

### Overview & Features

**PHStore** is a next-generation homebrew game store engineered specifically for jailbroken PlayStation 4 consoles running **GoldHEN** (Firmware 5.05 – 11.00). Built on a native C++ runtime powered by the lightweight QuickJS engine and React, PHStore delivers instantaneous UI navigation, background downloading, and automated installation without bogging down console resources.

* **Multi-Connection Segmented Download Engine:** Supports up to 8–16 simultaneous TCP download segments with instant pause, resume, and integrity verification.
* **Phone Bridge (Mobile Pairing via Local Wi-Fi):** Bypass console browser limitations and CAPTCHAs. Open links on your phone and automatically beam direct `/d/` download streams straight into your PS4 queue.
* **Zero-Lag Background Downloads:** Downloads proceed in the background while you browse or play other offline titles.
* **Disabled Screensaver by Default:** Eliminates idle interruptions and wallpaper decoding memory spikes, ensuring uninterrupted multi-gigabyte transfers.
* **Dynamic GitHub Catalog Feed:** Catalog updates, new titles, and patch fixes sync seamlessly over the cloud without requiring store re-installation.
* **Dual Language UI:** Instant one-button toggle between Turkish and English in Settings.

---

### Editions (Standard vs +TR)

PHStore is delivered in two separate standalone packages:

| Feature / Detail | Standard Edition (`PHStore.pkg`) | Turkish Edition (`PHStore+TR.pkg`) |
| :--- | :--- | :--- |
| **Title ID** | `PHST00002` | `PHST00003` |
| **Catalog Count** | 742+ Complete Games | 831+ Games & Patch Packs |
| **Turkish Translations** | Non-localized / Original releases | Includes 89+ Turkish localized game overlays & patches |
| **Patch Cards** | Standard game pages | Dedicated "Yamayı İndir" (Download Patch) cards |
| **Coexistence** | Can be installed side-by-side with +TR edition | Can be installed side-by-side with Standard edition |

---

### Installation Methods

#### Method 1: USB Flash Drive / External HDD (Recommended)
1. Prepare a USB flash drive or external hard drive formatted as **exFAT** or **FAT32** (exFAT is strongly recommended for large packages).
2. Download `PHStore.pkg` (or `PHStore+TR.pkg`).
3. Copy the `.pkg` file directly to the **root directory** of your USB drive (e.g., `E:\PHStore.pkg`).
4. Plug the USB drive into one of the USB ports of your PS4.
5. On your PS4, go to:
   **Settings** ➔ **GoldHEN** ➔ **Package Installer**.
6. Select `PHStore.pkg` from the list and press **X** to install.
7. Once finished, launch **PHStore** directly from the main PS4 home screen.

---

#### Method 2: Mobile Phone or PC via FTP (No USB Required)
If you do not have a USB drive on hand, you can push the PKG directly from an Android/iOS smartphone or PC over your local Wi-Fi network:

1. **Enable FTP on PS4:**
   * Open **GoldHEN** settings on your PS4.
   * Enable the **FTP Server** toggle (GoldHEN FTP runs on port `2121` or `21`).
   * Note the IP address displayed on your PS4 screen (e.g., `192.168.1.65`).
2. **Connect from Phone or PC:**
   * **Android / iOS:** Download any FTP client app (such as *AndroFTP*, *Material Files*, *Total Commander*, or *FTPManager*).
   * **PC:** Use *FileZilla* or *WinSCP*.
   * Enter the PS4 IP address and Port (`2121` or `21`). Username and password can be left blank (anonymous).
3. **Upload the PKG File:**
   * Navigate to the `/data/pkg` directory on your PS4 internal storage. (If the `pkg` folder does not exist under `/data`, create it).
   * Transfer `PHStore.pkg` into `/data/pkg/`.
4. **Install on Console:**
   * On your PS4, go to **Settings** ➔ **GoldHEN** ➔ **Package Installer**.
   * GoldHEN will automatically discover the `.pkg` placed inside `/data/pkg`. Press **X** to install.
   * After installation, you can delete the PKG file from `/data/pkg` to free up HDD space.

---

#### Method 3: Remote Package Installer (RPI)
1. Ensure the **Remote Package Installer** daemon is running on your PS4 (or enabled in GoldHEN).
2. Use tools such as *DirectPackageInstaller*, *PS4-Package-Sender*, or *Fluffy* on your PC.
3. Select `PHStore.pkg` and send it directly to your PS4 IP address.

---

### How-To: Phone Bridge & VikingFile Link Catcher

Certain hosters (such as **VikingFile**) protect download pages with CAPTCHA verification, Cloudflare checks, or countdown timers that cannot be solved easily with a DualShock 4 controller. 

**PHStore Phone Bridge** lets you handle the human verification on your smartphone, capture the generated direct `/d/` download link, and push it straight to the PS4!

#### Video Tutorial
Watch the step-by-step video tutorial by Burak Demir:
* 🎬 **YouTube Guide:** [VikingFile Link Yakalama ve Gönderme Rehberi](https://youtu.be/l8aR9_PvJ4o)

---

#### Manual Method (Quick & Easy)
1. Keep **PHStore** open on your PS4 on the **İndirmeler (Downloads)** tab where an item is waiting for a link.
2. On your smartphone browser (connected to the same Wi-Fi), open the pairing URL displayed on the console (e.g., `http://192.168.1.65:1903`).
3. Enter the numeric pairing code shown on your TV screen. The page will verify pairing and display the target game title and expected PKG filename.
4. Tap **"VikingFile sayfasını aç" (Open VikingFile page)**.
5. In the new browser tab:
   * Complete any CAPTCHA if prompted.
   * Wait for the countdown timer to reach 0.
   * When the actual **"Download"** button appears, **long-press** it and select **"Copy link address"**.
   * *Note: The URL must be formatted as `https://vikingfile.com/d/.../filename.pkg` or `https://vik1ngfile.site/d/.../filename.pkg`. Copying the `/f/...` page URL is NOT valid.*
6. Switch back to the PHStore Phone Bridge tab.
7. Open the **"Bağlantıyı elle gönder" (Send link manually)** section, paste the copied `/d/` link into the box, and tap **"PS4'e Gönder" (Send to PS4)**.
8. The console validates the file header and size, and download begins immediately on your PS4!

---

#### Automatic Bookmarklet Method
For seamless 1-tap capture on your phone:
1. On the PHStore mobile pairing page, tap **"Yakalama kodunu kopyala" (Copy capture code)**.
2. Bookmark any page in your mobile browser, then **edit the bookmark**:
   * Set the title to: `PHStore Yakala`
   * In the URL/Address field, delete everything and paste the copied script. *(Ensure the code starts with `javascript:`)*.
3. Tap **"VikingFile sayfasını aç"** from the PHStore mobile screen.
4. Once the VikingFile page opens, run the **PHStore Yakala** bookmark from your browser's bookmarks menu (or type `PHStore Yakala` into your browser address bar and select the bookmark).
5. A green status banner will appear at the top: *"PHStore bağlantıyı bekliyor. CAPTCHA varsa doğrula…"*
6. Solve the CAPTCHA and wait out the timer. As soon as the genuine download button is generated, the script catches it automatically and redirects you back to PHStore, transmitting the link to your console!

---

#### Understanding Status Indicators
* **Eşleşti (Paired):** Phone is connected to the PS4; download has not started yet.
* **Waiting banner displayed on VikingFile:** The capture script is active and listening for the download link.
* **Automatic redirect back to PHStore:** Link caught and sent to console; validation in progress.
* **Progress bar moving / MB increasing on PS4:** Download is actively streaming to your PS4!

---

#### Troubleshooting Link Capture
* **No waiting banner appears:** The bookmarklet did not execute. Make sure the URL begins with `javascript:` and is executed inside the VikingFile tab, not the PHStore tab.
* **Banner appears but does not redirect:** The countdown has not finished or an ad popup intercepted focus. Tap the Download button again or use the Manual Copy method.
* **Session Expired:** Pairing tokens are valid for ~10 minutes. If expired, refresh the Phone Bridge on PS4 and pair again with a fresh code.
* **Network Isolation:** Ensure your phone is not using cellular data or a VPN that isolates it from the local PS4 subnet.

---

### Recommended Settings & Best Practices

In PHStore, navigate to **Ayarlar (Settings)** to fine-tune download parameters:

* **Download Connections (İndirme Bağlantı Sayısı):**
  * **Recommended for VikingFile:** Set to **8 Connections**. Setting to 16 connections may trigger rate limiting (HTTP 429 Too Many Requests) on certain CDN nodes, causing the engine to fall back to a single stream.
  * **Recommended for WebArchive / Direct Hosts:** **8 or 16 Connections** will yield full bandwidth saturation.
* **Speed Limit (Hız Sınırı):** Keep set to **Sınırsız (Unlimited)** unless you need to preserve bandwidth for other home devices.
* **Screensaver (Ekran Koruyucu):** In v02.42+, the screensaver is permanently disabled to eliminate background RAM overhead and ensure flawless high-speed transfers.

---

<br />

---

## 🇹🇷 Türkçe Kullanım ve Kurulum Rehberi

### İçindekiler
1. [Genel Bakış ve Özellikler](#genel-bakış-ve-özellikler)
2. [Sürümler (Standart PHStore vs PHStore+TR)](#sürümler-standart-phstore-vs-phstoretr)
3. [Kurulum Yöntemleri](#kurulum-yöntemleri)
   - [Yöntem 1: USB Bellek / Harici Hard Disk ile (Önerilen)](#yöntem-1-usb-bellek--harici-hard-disk-ile-kurulum-önerilen)
   - [Yöntem 2: Telefondan veya PC'den FTP ile Gönderme (USB Olmadan)](#yöntem-2-telefondan-veya-pcden-ftp-ile-gönderme-usb-gerektirmez)
   - [Yöntem 3: Remote Package Installer (RPI) ile](#yöntem-3-remote-package-installer-rpi-ile)
4. [Rehber: Telefon Köprüsü ve VikingFile Link Yakalama](#rehber-telefon-köprüsü-ve-vikingfile-link-yakalama)
   - [Video Anlatımı](#video-anlatımı)
   - [Manuel Yöntem (Hızlı ve Kolay)](#manuel-yöntem-hızlı-ve-kolay)
   - [Otomatik Yer İmi (Bookmarklet) Yöntemi](#otomatik-yer-imi-bookmarklet-yöntemi)
   - [Durum Bildirimleri ve Aşama Takibi](#durum-bildirimleri-ve-aşama-takibi)
   - [Olası Sorunlar ve Çözümleri](#olası-sorunlar-ve-çözümleri)
5. [Önerilen Ayarlar ve İpuçları](#önerilen-ayarlar-ve-i̇puçları)
6. [Geliştirici ve İletişim](#geliştirici-ve-i̇letişim)

---

### Genel Bakış ve Özellikler

**PHStore**, GoldHEN (5.05 – 11.00 arası tüm sürümler) yüklü kırık PlayStation 4 konsolları için sıfırdan geliştirilmiş, yüksek performanslı ve modern bir homebrew oyun ve yama mağazasıdır. QuickJS motoru ve C++ native çekirdek üzerinde koşan uygulama, PS4 donanımını yormadan akıcı bir arayüz ve stabil arka plan indirmeleri sunar.

* **Çoklu Bağlantılı Parçalı İndirme Motoru:** 8 ila 16 eşzamanlı bağlantı desteği, duraklatma, devam ettirme ve otomatik dosya bütünlüğü kontrolü.
* **Telefon Köprüsü (Phone Bridge):** PS4 kumandasıyla link yazma veya CAPTCHA çözme eziyetine son! Aynı Wi-Fi'daki telefonunuzdan konsola bağlanıp VikingFile veya direkt indirme linklerini saniyeler içinde PS4'e aktarın.
* **Sıfır Donma & Arka Plan Desteği:** İndirmeler siz mağazada gezinirken veya başka bir ekrandayken arka planda hız kesmeden sürer.
* **Kaldırılmış Ekran Koruyucu (v02.42):** Boşta beklerken bellek şişmesini ve gereksiz görsel yüklemelerini önlemek adına ekran koruyucu tamamen kaldırılmış, sistem stabilitesi en üst seviyeye çıkarılmıştır.
* **Buluttan Canlı Katalog:** Yeni eklenen oyunlar, güncellemeler ve Türkçe yamalar GitHub üzerinden anında güncellenir; uygulamayı tekrar tekrar kurmanız gerekmez.
* **Çift Dil Desteği:** Ayarlar ekranından tek tuşla Türkçe ve İngilizce arasında geçiş imkanı.

---

### Sürümler (Standart PHStore vs PHStore+TR)

PHStore iki farklı resmi `.pkg` paketi olarak sunulmaktadır:

| Özellik / Detay | Standart Sürüm (`PHStore.pkg`) | Türkçe Sürüm (`PHStore+TR.pkg`) |
| :--- | :--- | :--- |
| **Title ID** | `PHST00002` | `PHST00003` |
| **Katalog Sayısı** | 742+ Tam Oyun | 831+ Oyun ve Özel Yama Paketi |
| **Türkçe Çeviriler** | Orijinal / Global sürümler | 89+ Özel Türkçe yama ve Türkçe içerikli oyun |
| **Yama Kartları** | Standart oyun detayları | Ayrı "Yamayı İndir" butonlu özel kartlar |
| **Birlikte Kullanım** | +TR sürümüyle yan yana kurulabilir | Standart sürümle yan yana kurulabilir |

---

### Kurulum Yöntemleri

#### Yöntem 1: USB Bellek / Harici Hard Disk ile Kurulum (Önerilen)
1. USB flash belleğinizi veya harici diskinizi **exFAT** veya **FAT32** olarak biçimlendirin (büyük dosyalar için exFAT önerilir).
2. İndirdiğiniz `PHStore.pkg` (veya `PHStore+TR.pkg`) dosyasını USB diskinizin **ana dizinine (root)** kopyalayın (Örn: `E:\PHStore.pkg`).
3. USB belleğinizi PS4'ün USB girişine takın.
4. PS4 menüsünden:
   **Ayarlar** ➔ **GoldHEN** ➔ **Package Installer** bölümüne girin.
5. Listede görünen `PHStore.pkg` dosyasının üzerine gelip **X** tuşuna basarak kurulumu başlatın.
6. Kurulum bittiğinde ana ekrana gelen PHStore simgesine tıklayarak mağazayı başlatabilirsiniz.

---

#### Yöntem 2: Telefondan veya PC'den FTP ile Gönderme (USB Gerektirmez)
Elinizde boş USB bellek yoksa, Android/iOS telefonunuzdan veya bilgisayarınızdan dosyayı yerel ağ üzerinden konsola gönderebilirsiniz:

1. **PS4'te FTP'yi Açın:**
   * PS4'te **GoldHEN** ayarlarına girip **FTP Server** seçeneğini etkinleştirin (Port genelde `2121` veya `21` olur).
   * Ekranda görünen PS4 IP adresini not edin (Örn: `192.168.1.65`).
2. **Telefondan veya PC'den Bağlanın:**
   * **Telefon için:** *AndroFTP*, *Material Files* veya *Total Commander* gibi ücretsiz bir FTP uygulaması indirin.
   * **PC için:** *FileZilla* programını açın.
   * Sunucu kısmına PS4 IP adresini, Port kısmına `2121` yazıp bağlanın (Kullanıcı adı ve şifre gerekmez / Anonim).
3. **PKG Dosyasını Gönderin:**
   * PS4 hafızasındaki `/data/pkg` klasörüne girin (Eğer `pkg` klasörü yoksa `/data` içinde oluşturun).
   * `PHStore.pkg` dosyasını bu klasörün içine yükleyin.
4. **Konsoldan Kurun:**
   * PS4'te **Ayarlar** ➔ **GoldHEN** ➔ **Package Installer** menüsüne girin.
   * GoldHEN `/data/pkg` içine attığınız dosyayı otomatik görecektir; **X** ile kurulumu tamamlayın.
   * Kurulum bittikten sonra hafızada yer kaplamaması için FTP'den `/data/pkg` içindeki `.pkg` dosyasını silebilirsiniz.

---

#### Yöntem 3: Remote Package Installer (RPI) ile
1. PS4'ünüzde **Remote Package Installer** uygulamasını çalıştırın veya GoldHEN RPI özelliğini açın.
2. PC'nizde *PS4-Package-Sender*, *DirectPackageInstaller* veya *Fluffy* programını açın.
3. `PHStore.pkg` dosyasını seçip PS4'ünüze ağ üzerinden doğrudan göndererek kurun.

---

### Rehber: Telefon Köprüsü ve VikingFile Link Yakalama

VikingFile gibi bazı dosya barındırıcıları indirme linklerini CAPTCHA doğrulamaları, Cloudflare kontrolleri veya geri sayım sayaçları arkasında tutar. PS4'ün dahili tarayıcısı bu adımları geçmek için yetersiz kaldığında **PHStore Telefon Köprüsü** devreye girer.

İşlemi cep telefonunuzdan yapıp oluşan indirme linkini tek tuşla konsola aktarabilirsiniz!

#### Video Anlatımı
Tüm adımları canlı olarak Burak Demir'in hazırladığı video rehberden izleyebilirsiniz:
* 🎬 **YouTube Video Rehberi:** [https://youtu.be/l8aR9_PvJ4o](https://youtu.be/l8aR9_PvJ4o)

---

#### Manuel Yöntem (Hızlı ve Kolay)
1. PS4'te PHStore açık kalsın ve telefon bağlantısı bekleyen **İndirmeler** sekmesinde durun.
2. Cep telefonunuzun tarayıcısını açıp konsolda yazan adrese gidin (Örn: `http://192.168.1.65:1903`).
3. Konsol ekranındaki eşleştirme kodunu girin. Telefonda ilgili oyunun ve beklenen PKG dosyasının adı görünecektir.
4. **"VikingFile sayfasını aç"** düğmesine basın.
5. Açılan VikingFile sekmesinde:
   * Varsa CAPTCHA doğrulamasını tamamlayın.
   * Sitenin geri sayım süresini bekleyin.
   * Asıl indirme düğmesi (**Download**) hazır olduğunda üzerine **uzun basın** ve **"Bağlantı adresini kopyala"** seçeneğini seçin.
   * *Dikkat: Kopyalanan adres `https://vik1ngfile.site/d/.../dosya.pkg` veya `https://vikingfile.com/d/.../dosya.pkg` biçiminde olmalıdır. Sayfanın `/f/...` adresini kopyalamak geçersizdir.*
6. Telefonda PHStore sekmesine geri dönün.
7. **"Bağlantıyı elle gönder"** bölümünü açın, kopyaladığınız `/d/` linkini yapıştırıp **"PS4’e gönder"** butonuna basın.
8. PS4 dosya boyutunu ve başlığını doğrulayarak indirmeyi doğrudan konsolda başlatacaktır.

---

#### Otomatik Yer İmi (Bookmarklet) Yöntemi
Telefonunuzda tek dokunuşla yakalamak için:
1. Telefonda PHStore eşleştirme sayfasındayken **"Yakalama kodunu kopyala"** düğmesine basın.
2. Tarayıcınızda herhangi bir sayfayı yer imlerine ekleyin ve bu yer imini **düzenleyin**:
   * Adını: `PHStore Yakala` yapın.
   * URL/Adres kısmındaki her şeyi silip kopyaladığınız kodu yapıştırın *(Adresin başında `javascript:` olduğundan emin olun)*.
3. PHStore sayfasına dönüp **"VikingFile sayfasını aç"** düğmesine basın.
4. VikingFile sekmesi açıldığında tarayıcınızın yer imlerinden **PHStore Yakala** kaydını çalıştırın (ya da adres çubuğuna adını yazıp çıkan yer imine dokunun).
5. Sayfanın en üstünde: *"PHStore bağlantıyı bekliyor. CAPTCHA varsa doğrula…"* yeşil bandı çıkar.
6. CAPTCHA ve süreyi bitirin. İndirme butonu oluştuğu anda kod bunu otomatik yakalayacak, sizi PHStore sayfasına geri yönlendirip linki konsola iletecektir!

---

#### Durum Bildirimleri ve Aşama Takibi
* **Eşleşti:** Telefon konsola bağlandı; indirme henüz başlamadı.
* **Üstte bekleme bandı çıktı:** VikingFile sekmesindeki yakalama kodu aktif olarak linki dinliyor.
* **PHStore sayfasına otomatik döndü:** Link yakalandı ve konsola gönderildi; PS4 doğrulama yapıyor.
* **Konsolda MB artıyor ve ilerleme çubuğu doluyor:** Gerçek indirme başarıyla başladı!

---

#### Olası Sorunlar ve Çözümleri
* **Bekleme bandı çıkmıyorsa:** Yer imi URL alanının başında `javascript:` olduğundan ve yer imini VikingFile sekmesindeyken çalıştırdığınızdan emin olun.
* **Band var ama linki yakalamıyorsa:** Sayaç bitmemiş veya site başka bir popup açmış olabilir. Asıl Download butonunun çıktığını teyit edin ya da manuel kopyalama yöntemini kullanın.
* **Oturum Zaman Aşımı:** Konsoldaki kod yaklaşık 10 dakika geçerlidir. Süre dolarsa konsoldan oturumu yenileyip telefondan yeni kodla eşleşin.
* **Ağ İzolasyonu:** Telefonunuzun mobil veride olmadığından, PS4 ile tamamen aynı yerel Wi-Fi ağına bağlı olduğundan emin olun.

---

### Önerilen Ayarlar ve İpuçları

PHStore içerisindeki **Ayarlar** menüsünden aşağıdaki optimizasyonları yapabilirsiniz:

* **İndirme Bağlantı Sayısı (Download Connections):**
  * **VikingFile İndirmeleri İçin:** **8 Bağlantı** seçeneğini kullanın. 16 bağlantı yapıldığında VikingFile sunucuları HTTP 429 (Çok Fazla İstek) hatası verip indirmeyi tek bağlantıya düşürebilir; 8 bağlantı maksimum hız ve stabilite sağlar.
  * **WebArchive ve Diğer Doğrudan İndirmeler İçin:** **8 veya 16 Bağlantı** internet bant genişliğinizi sonuna kadar kullanır.
* **Hız Sınırı:** İnternetinizi başka cihazlar yoğun kullanmıyorsa **Sınırsız** olarak bırakın.
* **Ekran Koruyucu:** v02.42 ile birlikte ekran koruyucu devre dışı bırakılmıştır; konsolu indirme sırasında kendi haline bıraksanız dahi hiçbir takılma veya çökme yaşanmaz.

---

### Geliştirici ve İletişim

* 🎥 **YouTube:** [@burakdemirph](https://www.youtube.com/@burakdemirph)
* 🐙 **GitHub:** [PratikHackTR](https://github.com/PratikHackTR)
* 📸 **Instagram:** [burak_demirr01](https://www.instagram.com/burak_demirr01/)
* 🎬 **VikingFile Eğitim Videosu:** [https://youtu.be/l8aR9_PvJ4o](https://youtu.be/l8aR9_PvJ4o)

---
*Developed with ❤️ by Burak Demir (PratikHackTR) for the PS4 Homebrew Community.*
