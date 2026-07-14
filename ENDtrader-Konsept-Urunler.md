# ENDtrader Motorundan 10 Konsept Ürün
### Her bileşen → kriptodan arındırılmış, kurumsal, Katar-uyumlu bir ürün konsepti

**Bağlam:** `ENDtrader-Katar-Giris-Analizi.md` Bölüm 6.1 tablosundaki 10 bileşenin her biri için birer konsept
ürün. Hepsi **regüle-olmayan B2B teknoloji** (parayı tutmaz, kimse adına işlem yapmaz) → QFC B2B FinTech
lisansı, %100 yabancı sahiplik. Varlık sınıfı: hisse/sukuk/FX/tokenize RWA (kripto DEĞİL).
**Rapor tarihi:** 14 Temmuz 2026.

> **Marka notu:** Aşağıdaki ürün adları **yer-tutucudur** (placeholder). Modüler bir aile olarak düşünülebilir:
> tek çekirdek motor + ayrı satılabilen 10 modül. Çekirdek konumlandırma: *"Lisanslı kurumlar için, gelen
> QFMA regülasyonuna hazır, rejim-adaptif algo-yönetişim & gözetim altyapısı."*

> **Dürüstlük etiketi:** Bunlar **konsept taslaklarıdır**, doğrulanmış iş planları değil. Ürün-kategori ve
> rakip zemini **Orta-Yüksek** güvende (gerçek pazar segmentleri). "Katar niş boşluğu" ve talep **Orta**
> güvende — saha doğrulaması (QFMA/QFCRA + broker görüşmeleri) şart. Bahis gücü sıralaması, rakip-yoğunluğu
> analizinden gelir (Bölüm 6.1): **RegTech/SupTech kümesi güçlü, EMS/OMS/backtest yerleşik-dolu.**

---

## 🟢 Güçlü küme (Katar-öncelikli + gelen regülasyonla hizalı + niş boş)

### 1. **PreTrade Guard** — İşlem-öncesi Uygunluk & Risk Geçidi
- **Ne:** Her emir/sinyal borsaya gitmeden önce çok-katmanlı kontrolden geçer (mandat, limit, piyasa-koşulu,
  tahta derinliği); reddedilenler **gerekçesiyle** loglanır. Kurumun OMS'i ile borsa arasında duran bir "geçit".
- **Sektör/alıcı:** RegTech/TradingTech · broker, varlık yöneticisi, prop-desk.
- **ENDtrader'dan:** SOP v2 K1/K2/K3 doğrulama katmanları + `order_book_depth_threshold` kontrolü + fail-closed mimari.
- **Değer:** "Kötü emir" piyasaya hiç ulaşmaz; her ret denetlenebilir kayıt bırakır.
- **Katar/regülasyon:** QFMA taslağı (algo sistem testi/manipülasyon önleme) ile hizalı.
- **MVP:** Broker/OMS önüne konan bir kural-motoru API + config UI + gerekçe-loglu ret akışı; tek varlık sınıfı (hisse).
- **Rakip/zorluk:** OMS'ler bunu paketli sunar → **fark:** bağımsız, çok-varlık, **Şeriat-farkında** geçit.
- **Bahis gücü:** ⭐⭐⭐⭐ (bundle çekirdeği).

### 2. **RiskFirewall** — Gerçek-zamanlı Risk Limitleri + Kill-Switch
- **Ne:** Hesap-seviyesi kalkanlar: günlük zarar kilidi, portföy ısısı/maruziyet limiti, ardışık-zarar durdurma,
  olay kilidi ve **tek tuşla acil durdurma (kill-switch)**.
- **Sektör/alıcı:** RegTech/RiskTech · prop-desk, broker, likidite sağlayıcı.
- **ENDtrader'dan:** §6 fail-closed risk kalkanları motoru (günlük zarar, ısı, cooldown, olay kilidi, max pozisyon).
- **Değer:** Otomasyon çığırından çıkarsa saniyeler içinde durur; maruziyet sert tavanlanır.
- **Katar/regülasyon:** QFCRA CTRL 2020 "etkin sistem-kontrol + risk yönetimi" *(yürürlükte)* + QFMA gerçek-zamanlı izleme.
- **MVP:** Broker API'sini saran risk-limit servisi + kill-switch dashboard'u.
- **Rakip/zorluk:** Kavram evrensel; fark = kurulum kolaylığı + tek panelde çok-hesap.
- **Bahis gücü:** ⭐⭐⭐⭐⭐ (en evrensel-zorunlu; kill-switch/limit her yerde gerekir).

### 3. **SurveilLog** — Karar Günlüğü + Trade Surveillance + Açıklanabilirlik
- **Ne:** Her kararın + gerekçesinin + reddin **değiştirilemez** kaydı; regülatöre-hazır işlem yeniden-kurgusu
  (trade reconstruction); AI/algo kararının açıklanabilirlik görünümü.
- **Sektör/alıcı:** RegTech/SupTech · uyum (compliance) ekipleri, MLRO.
- **ENDtrader'dan:** `v3_decision_log` + heartbeat + `[SOP v2 Kalkanı]` gerekçe önekleri + AI gerekçe loglama.
- **Değer:** "Neden bu işlem yapıldı/yapılmadı?" sorusunun kanıtlı cevabı bir tık ötede.
- **Katar/regülasyon:** QFMA taslağı **doğrudan** — "karar kriterlerinin ifşası + izleme/denetim + açıklanabilirlik".
- **MVP:** Karar akışı yutucu (ingestion) + değiştirilemez depo + sorgu/dışa-aktarım + açıklanabilirlik ekranı.
- **Rakip/zorluk:** NASDAQ SMARTS, SteelEye, OneSumX var ama pahalı/ağır → fark = hafif + algo-yerli + Katar-fiyatlı.
- **Bahis gücü:** ⭐⭐⭐⭐⭐ (Katar için en iyi **zamanlanmış** ürün — açıklanabilirlik zorunluluğu geliyor).

### 9. **OversightConsole** — Gerçek-zamanlı Gözetim Konsolu (İnsan-Döngüde)
- **Ne:** Tüm hesap/stratejilerin canlı izlenmesi, heartbeat sağlık durumu, alarmlar (Telegram/e-posta),
  tek-tuş müdahale ve **insan-onay geçitleri** (yüksek-riskli karar önce insana sorulur).
- **Sektör/alıcı:** SupTech/SaaS · risk/uyum gözetmenleri, operasyon.
- **ENDtrader'dan:** Çok-kiracılı mimari + heartbeat + equity snapshot + Telegram bildirim + admin dashboard/modal.
- **Değer:** "Kara-kutu" otomasyona insan gözü ve freni; çok-hesabı tek ekrandan yönet.
- **Katar/regülasyon:** QFMA taslağı **doğrudan** — "**anlamlı insan gözetimi**" + gerçek-zamanlı izleme.
- **MVP:** Bağlı hesaplar üstünde izleme dashboard'u + alarm + müdahale kontrolleri + onay-geçidi.
- **Rakip/zorluk:** Surveillance dashboard'ları var; fark = algo-yerli + insan-döngü onay akışı.
- **Bahis gücü:** ⭐⭐⭐⭐ (insan-gözetimi zorunluluğuna birebir oturur).

> **Amiral gemisi önerisi:** 1+2+3+9'u **tek üründe** paketleyin → **"Algo-Governance & Surveillance Suite"**.
> Bu, ENDtrader'ın gerçek farkının (fail-closed doğrulama + karar loglama + insan gözetimi) bulunduğu,
> Katar-öncelikli ve yerleşik-boş olan kamadır.

---

## 🟡 Orta küme (yaşayabilir ama niş / kısmen kancasız)

### 5. **RegimeIQ** — Piyasa-Rejimi Analitiği / Sinyal Servisi
- **Ne:** Enstrüman başına piyasa durumunu (trend/yatay/kaos) ATR/ADX/Hurst + AI ile sınıflar; veri/analitik feed veya API.
- **Sektör/alıcı:** AI/Market Analytics · quant ekipler, PM'ler.
- **ENDtrader'dan:** §3 rejim tespiti (auto/coin_specific/Hurst) + AI rejim seçici.
- **Değer:** "Şu an hangi rejimdeyiz?" — strateji seçimi/risk ayarı için tek girdi.
- **Katar/regülasyon:** Doğrudan kanca yok — saf ürün değeri.
- **MVP:** Rejim API + dashboard; birkaç varlık.
- **Rakip/zorluk:** Analitik feed'leri bol; farklılaşma zor.
- **Bahis gücü:** ⭐⭐ (tek başına zayıf; suite'e **özellik** olarak güçlü).

### 8. **SizeWise** — Pozisyon Boyutlandırma / Risk-Bütçeleme Motoru
- **Ne:** Compound / strict / risk-bazlı boyutlandırma + volatilite-ölçekli kaldıraç; "bu işlemde ne kadar riske gireyim?" cevabı.
- **Sektör/alıcı:** RiskTech/WealthTech · küçük-orta fon, PM.
- **ENDtrader'dan:** §7 boyutlandırma & kaldıraç motoru (risk_per_trade, volatilite kaldıracı, compound).
- **Değer:** Tutarlı, kurallı sermaye tahsisi; duygu değil formül.
- **Katar/regülasyon:** QFCRA CTRL risk yönetimi *(genel)*.
- **MVP:** Sizing API + basit UI; risk-bütçe raporu.
- **Rakip/zorluk:** Üst segmentte MSCI/Axioma ağır; **küçük firma** segmentinde hafif araç yeri var.
- **Bahis gücü:** ⭐⭐⭐ (küçük-firma nişinde makul).

### 10. **EventShield** — Olay/Haber-Riski Bekçisi
- **Ne:** Ekonomik takvim + haber-tetikli işlem durdurma/yön kısıtı; yüksek-etkili olay çevresinde stratejileri otomatik duraklatır.
- **Sektör/alıcı:** Market Data/RiskTech · desk, risk.
- **ENDtrader'dan:** §6 haber kalkanı + takvim kilidi + `v3-news-scraper` beslemesi.
- **Değer:** "Haber patlamasında pozisyon açma" hatasını sistemik olarak keser.
- **Katar/regülasyon:** Operasyonel risk; dolaylı.
- **MVP:** Takvim+haber feed'i + durdurma orkestrasyon katmanı; bir kurumsal risk-motoruna eklenti.
- **Rakip/zorluk:** Veri tarafı ağır (RavenPack/Bloomberg); **durdurma orkestrasyonu** katmanı daha hafif.
- **Bahis gücü:** ⭐⭐⭐ (suite eklentisi olarak iyi).

---

## 🔴 Zayıf küme (dev yerleşikler — cepheden girme)

### 4. **QuantLab** — Backtesting & Strateji Doğrulama Sandbox'ı
- **Ne:** Walk-forward, gerçekçi komisyon/kayma, parametre taraması, equity eğrisi, enstrüman kırılımı.
- **Sektör/alıcı:** Quant/WealthTech · quant ekip, varlık yöneticisi.
- **ENDtrader'dan:** §12 backtest altyapısı (exact-config, dinamik maliyet, optimizer).
- **Katar/regülasyon:** QFMA taslağı — devreye-alma öncesi test/validasyon.
- **Rakip/zorluk:** **Bloomberg, Refinitiv, QuantConnect** hâkim → tek başına **kötü bahis**.
- **Bahis gücü:** ⭐⭐ tek başına; **suite içinde "test-before-deploy kanıtı"** olarak ⭐⭐⭐⭐ (regülatöre gösterilecek test izi).

### 6. **ExecEngine** — Execution Management (EMS) / Execution Algo
- **Ne:** Maker-chase, limit-TP, market failsafe icra algoları; akıllı emir yönlendirme.
- **Sektör/alıcı:** TradingTech · işlem masaları.
- **ENDtrader'dan:** §8 icra (maker chase, post-only, failsafe) + stop/TP hesap mantığı.
- **Katar/regülasyon:** QSE algo/DMA sahnesi emekleme (nascent).
- **Rakip/zorluk:** **Trading Technologies, FlexTrade, Quod** çok güçlü → **cepheden girme.**
- **Bahis gücü:** ⭐ tek başına; yalnız gömülü modül olarak anlamlı.

### 7. **PositionKeeper** — OMS-lite Pozisyon Yaşam Döngüsü
- **Ne:** Pozisyon takibi, native+yazılım SL/TP yedeği, stale/trailing/rejim çıkışı, yetim-pozisyon uzlaştırma.
- **Sektör/alıcı:** TradingTech · küçük fon/broker.
- **ENDtrader'dan:** §9 pozisyon yönetimi & çıkışlar + yetim pozisyon koruması.
- **Katar/regülasyon:** Operasyonel; doğrudan kanca yok.
- **Rakip/zorluk:** OMS vendor'ları (Charles River, Bloomberg AIM) hâkim.
- **Bahis gücü:** ⭐⭐ (suite'in operasyon bileşeni olarak; tek başına zayıf).

---

## Özet Öncelik Sırası (bahis gücüne göre)

| Öncelik | Ürün | Küme | Neden |
|---|---|---|---|
| 1 | **RiskFirewall** (2) | 🟢 | En evrensel-zorunlu; kill-switch/limit her kurumda gerekir |
| 2 | **SurveilLog** (3) | 🟢 | Katar için en iyi zamanlanmış (açıklanabilirlik zorunluluğu geliyor) |
| 3 | **OversightConsole** (9) | 🟢 | "Anlamlı insan gözetimi" zorunluluğuna birebir |
| 4 | **PreTrade Guard** (1) | 🟢 | Bundle çekirdeği; Şeriat-farkında geçit farkı |
| 5 | SizeWise (8) / EventShield (10) | 🟡 | Küçük-firma nişi / suite eklentisi |
| 6 | RegimeIQ (5) | 🟡 | Tek başına zayıf, suite özelliği olarak güçlü |
| 7 | QuantLab (4) | 🔴→🟢 | Tek başına dev-dolu; suite'te "test kanıtı" olarak değerli |
| 8 | ExecEngine (6) / PositionKeeper (7) | 🔴 | Yerleşik-dolu; yalnız gömülü modül |

**Tavsiye:** Tek ürün seçmek yerine **1+2+3+9 = "Algo-Governance & Surveillance Suite"** amiral gemisi;
5+8+10 suite özellikleri; 4 "test-before-deploy kanıtı" modülü; 6+7 gömülü. Kripto geliri (asıl ürün)
paralelde **BAE/Bahreyn**'de. Sonraki adım: bu amiral gemisi için tek-sayfalık ürün tanımı + QFTH pitch taslağı.
