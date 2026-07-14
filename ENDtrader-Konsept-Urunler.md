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
> güvende — saha doğrulaması (QFMA/QFCRA + broker görüşmeleri) şart. Alıcı-kitlesi bölümlerinde anılan Katar
> firmaları **segment örneğidir** (illüstratif), teyitli müşteri adayı değil. Bahis gücü sıralaması,
> rakip-yoğunluğu analizinden gelir (Bölüm 6.1): **RegTech/SupTech kümesi güçlü, EMS/OMS/backtest yerleşik-dolu.**

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
- **🎯 Ne işe yarıyor (detay):** Bir kurumun otomatik/yarı-otomatik akan emirlerinin **her biri**, borsaya
  ulaşmadan önce bir denetim geçidinden geçer: yatırım mandatına uygun mu, limit aşıyor mu, piyasa koşulu
  (likidite/derinlik/rejim) elverişli mi? Uygunsuz emir **kaynakta** durur ve neden durduğu gerekçeli
  kaydedilir. *Öncesi:* emirler doğrudan/OMS ile borsaya gider, hata piyasada görülür. *Sonrası:* araya
  denetlenebilir, kurallı, "hayır" diyebilen bir katman girer — "fat finger" ve mandat-ihlali riski kaynağında kesilir.
- **👥 Alıcı kitlesi (detay):** *Ekonomik alıcı:* Head of Trading / COO (bütçe onayı). *Kullanıcı-şampiyon:*
  trading desk + uyum ekibi (günlük kullanan). *Teknik onay:* CTO / Head of Technology (OMS entegrasyonu).
  *Segment:* QSE üyesi aracı kurumlar, QFC-lisanslı brokerler, prop-desk. *Katar örnek (illüstratif):* QNB
  Financial Services, The Group Securities gibi aracı kurumlar. *GCC genişleme:* EFG Hermes ve BAE/Suudi'deki
  çok sayıda aktif aracı kurum.

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
- **🎯 Ne işe yarıyor (detay):** Kurumun tüm otomatik işlem akışına canlı bir "sigorta" koyar. Zarar/maruziyet/
  ardışık-kayıp eşiklerine dokunulduğunda yeni giriş **otomatik durur**; felaket anında gözetmen **tek tuşla
  bütün otomasyonu keser** (kill-switch). İç denetim ve regülatörün klasik sorusu — *"Bir algo kontrolden
  çıkarsa nasıl durduruyorsunuz?"* — bu ürünle somut bir cevaba kavuşur. Fark: kurallar fail-closed'dur,
  yani veri/bağlantı hatasında sistem "aç" değil "kapa" tarafına düşer.
- **👥 Alıcı kitlesi (detay):** *Ekonomik alıcı:* CRO / Head of Risk. *Kullanıcı-şampiyon:* risk masası + desk
  head. *Teknik onay:* CTO (borsa/broker API sarma). *Segment:* prop-trading desk, **piyasa yapıcı/likidite
  sağlayıcı** (Katar'da 2025'te başladı), banka hazine/trading masası. *Katar örnek (illüstratif):* Wasata
  gibi yeni piyasa yapıcılar; QNB/CBQ/Dukhan hazine masaları. *GCC:* prop firmaları ve market-maker'lar.

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
- **🎯 Ne işe yarıyor (detay):** Sistemin verdiği her kararı — ve **reddi** — zaman-damgalı, gerekçeli ve
  sonradan değiştirilemez biçimde saklar. Regülatör veya iç denetçi *"14 Temmuz'da şu işlem neden açıldı /
  neden açılmadı?"* dediğinde, olayın tüm bağlamı (hangi kural, hangi veri, hangi rejim) saniyeler içinde
  yeniden kurulur ve **insan-okunur bir gerekçeyle** sunulur. Manuel Excel/e-posta arşivinin ve "hafızadan
  açıklama"nın yerini alır. AI kullanılan yerlerde "kara kutu" sorununu şeffaflaştırır.
- **👥 Alıcı kitlesi (detay):** *Ekonomik alıcı:* CCO (Chief Compliance Officer) / MLRO. *Kullanıcı-şampiyon:*
  uyum/gözetim analisti, iç denetim. *Teknik onay:* CTO/CISO (değiştirilemez depo, veri-yerleşimi/data-residency).
  *Segment:* **her** QFMA/QFCRA-lisanslı firma + regülatör/borsa (SupTech alıcısı). *Katar örnek (illüstratif):*
  lisanslı tüm aracı kurum/varlık yöneticileri; QSE gözetim birimi. *GCC:* geniş — her yargı çevresinde uyum zorunlu.

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
- **🎯 Ne işe yarıyor (detay):** Bir gözetmenin, kaç tane olursa olsun tüm otomatik hesap ve stratejiyi **tek
  ekrandan** canlı izlemesini sağlar: hangi bot çalışıyor/durdu (heartbeat), açık maruziyet ne, bir şey ters
  giderse anında alarm. Kritik/yüksek-riskli kararlarda sistem otomatik yürütmez, **önce insana sorar**
  (onay geçidi). Böylece otomasyonun hızını korurken, regülatörün istediği "nihai kontrol insanda" ilkesini
  operasyonel hale getirir. Fark: genel dashboard'lar sadece *gösterir*; bu, izlemeyi **müdahale + onay**
  ile birleştirir.
- **👥 Alıcı kitlesi (detay):** *Ekonomik alıcı:* CRO / CCO. *Kullanıcı-şampiyon:* risk/uyum gözetmeni, desk
  supervisor. *Teknik onay:* CTO. *Segment:* otomasyon/algo koşan her firma + regülatör/borsa (SupTech).
  *Katar örnek (illüstratif):* piyasa yapıcı ve banka masalarının gözetim birimleri; QSE/QFMA denetim.
  *GCC:* algo benimseyen tüm buy-side/sell-side.

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
- **🎯 Ne işe yarıyor (detay):** Bir enstrümanın veya pazarın o an **hangi karakterdeki** piyasada olduğunu
  (yönlü trend / bant-içi yatay / düzensiz kaos) sürekli sınıflandırır ve bunu bir sinyal/skor olarak sunar.
  Portföy yöneticisinin "piyasa karakteri değişti mi, stratejimi değiştirmeli miyim?" sezgisini **nicel,
  tekrarlanabilir bir girdiye** çevirir; strateji aç/kapa veya risk ölçekleme kararlarını besler.
- **👥 Alıcı kitlesi (detay):** *Ekonomik alıcı:* CIO / Head of Portfolio Management. *Kullanıcı-şampiyon:*
  PM, quant analist. *Teknik onay:* veri/altyapı ekibi. *Segment:* varlık yöneticisi, çok-strateji fon,
  quant-desk. *Not:* tek başına bir "analitik feed" alıcısı diğer ürünlere göre dar; asıl gücü **suite içinde
  1/2/9'u besleyen ortak motor** olması.

### 8. **SizeWise** — Pozisyon Boyutlandırma / Risk-Bütçeleme Motoru
- **Ne:** Compound / strict / risk-bazlı boyutlandırma + volatilite-ölçekli kaldıraç; "bu işlemde ne kadar riske gireyim?" cevabı.
- **Sektör/alıcı:** RiskTech/WealthTech · küçük-orta fon, PM.
- **ENDtrader'dan:** §7 boyutlandırma & kaldıraç motoru (risk_per_trade, volatilite kaldıracı, compound).
- **Değer:** Tutarlı, kurallı sermaye tahsisi; duygu değil formül.
- **Katar/regülasyon:** QFCRA CTRL risk yönetimi *(genel)*.
- **MVP:** Sizing API + basit UI; risk-bütçe raporu.
- **Rakip/zorluk:** Üst segmentte MSCI/Axioma ağır; **küçük firma** segmentinde hafif araç yeri var.
- **Bahis gücü:** ⭐⭐⭐ (küçük-firma nişinde makul).
- **🎯 Ne işe yarıyor (detay):** "Bu pozisyona ne kadar sermaye/kaldıraç ayırayım?" sorusunu **kurallı**
  yanıtlar: hesabın risk-bütçesini (ör. işlem başına %X risk) alır, stop mesafesi ve volatiliteye göre uygun
  pozisyon büyüklüğünü hesaplar, kaldıracı volatiliteye göre kısar. Keyfi/duygusal boyutlandırmayı ortadan
  kaldırır; tutarlı, denetlenebilir bir sermaye tahsisi disiplini getirir.
- **👥 Alıcı kitlesi (detay):** *Ekonomik alıcı:* Head of Risk / kurucu-PM. *Kullanıcı-şampiyon:* PM, trader.
  *Teknik onay:* — (hafif entegrasyon). *Segment:* **küçük-orta** fon, family office, butik varlık yöneticisi
  (üst segment MSCI/Axioma'ya gider). *Katar/GCC:* yeni kurulan butik fonlar ve family office'ler için erişilebilir bir araç.

### 10. **EventShield** — Olay/Haber-Riski Bekçisi
- **Ne:** Ekonomik takvim + haber-tetikli işlem durdurma/yön kısıtı; yüksek-etkili olay çevresinde stratejileri otomatik duraklatır.
- **Sektör/alıcı:** Market Data/RiskTech · desk, risk.
- **ENDtrader'dan:** §6 haber kalkanı + takvim kilidi + `v3-news-scraper` beslemesi.
- **Değer:** "Haber patlamasında pozisyon açma" hatasını sistemik olarak keser.
- **Katar/regülasyon:** Operasyonel risk; dolaylı.
- **MVP:** Takvim+haber feed'i + durdurma orkestrasyon katmanı; bir kurumsal risk-motoruna eklenti.
- **Rakip/zorluk:** Veri tarafı ağır (RavenPack/Bloomberg); **durdurma orkestrasyonu** katmanı daha hafif.
- **Bahis gücü:** ⭐⭐⭐ (suite eklentisi olarak iyi).
- **🎯 Ne işe yarıyor (detay):** Ekonomik takvimi ve haber akışını sürekli izler; yüksek-etkili bir veri
  açıklaması veya haber patlaması yaklaştığında/gerçekleştiğinde **stratejileri otomatik duraklatır** veya
  yönünü kısıtlar (ör. yalnız pozisyon-azaltıcı işlemlere izin). Volatilite şoku anında körlemesine pozisyon
  açma hatasını **sistemik olarak** engeller — insan hatırlamaya kalmaz, sistem kuralı uygular.
- **👥 Alıcı kitlesi (detay):** *Ekonomik alıcı:* Head of Risk. *Kullanıcı-şampiyon:* risk masası, desk.
  *Teknik onay:* veri entegrasyonu ekibi. *Segment:* aktif/otomatik işlem yapan brokerler, prop-desk'ler,
  hazine masaları. *Not:* haber-verisi tarafını (RavenPack/Bloomberg) satın alıp üzerine **durdurma-orkestrasyon**
  katmanı olarak konumlanmak en gerçekçisi; veriyle rekabet etme.

---

## 🔴 Zayıf küme (dev yerleşikler — cepheden girme)

### 4. **QuantLab** — Backtesting & Strateji Doğrulama Sandbox'ı
- **Ne:** Walk-forward, gerçekçi komisyon/kayma, parametre taraması, equity eğrisi, enstrüman kırılımı.
- **Sektör/alıcı:** Quant/WealthTech · quant ekip, varlık yöneticisi.
- **ENDtrader'dan:** §12 backtest altyapısı (exact-config, dinamik maliyet, optimizer).
- **Katar/regülasyon:** QFMA taslağı — devreye-alma öncesi test/validasyon.
- **Rakip/zorluk:** **Bloomberg, Refinitiv, QuantConnect** hâkim → tek başına **kötü bahis**.
- **Bahis gücü:** ⭐⭐ tek başına; **suite içinde "test-before-deploy kanıtı"** olarak ⭐⭐⭐⭐ (regülatöre gösterilecek test izi).
- **🎯 Ne işe yarıyor (detay):** Bir stratejinin canlıya çıkmadan önce, gerçekçi komisyon/kayma ve çok-varlık
  koşullarında geçmiş veriyle nasıl davranacağını test eder; parametreleri tarar, walk-forward ile aşırı-uyumu
  (overfit) yakalar. Asıl kurumsal değeri: regülatörün "algoyu devreye almadan test/valide ettiniz mi?"
  beklentisine **belgeli kanıt** üretmesidir — yani sadece bir araştırma aracı değil, bir **uyum kaydı**.
- **👥 Alıcı kitlesi (detay):** *Ekonomik alıcı:* Head of Quant / CIO. *Kullanıcı-şampiyon:* quant araştırmacı,
  strateji geliştirici. *Teknik onay:* veri/altyapı ekibi. *Segment:* varlık yöneticisi, hedge fon, quant-desk.
  *Gerçekçi not:* Bloomberg/QuantConnect bu alanı doldurmuş ve Katar'da bağımsız quant alıcı **az** → bunu
  ayrı satmak yerine **suite'in "test-kanıtı" modülü** olarak konumla.

### 6. **ExecEngine** — Execution Management (EMS) / Execution Algo
- **Ne:** Maker-chase, limit-TP, market failsafe icra algoları; akıllı emir yönlendirme.
- **Sektör/alıcı:** TradingTech · işlem masaları.
- **ENDtrader'dan:** §8 icra (maker chase, post-only, failsafe) + stop/TP hesap mantığı.
- **Katar/regülasyon:** QSE algo/DMA sahnesi emekleme (nascent).
- **Rakip/zorluk:** **Trading Technologies, FlexTrade, Quod** çok güçlü → **cepheden girme.**
- **Bahis gücü:** ⭐ tek başına; yalnız gömülü modül olarak anlamlı.
- **🎯 Ne işe yarıyor (detay):** Bir emri piyasaya **en iyi koşulla** ulaştırır: önce maker (post-only) fiyatla
  dener, dolmazsa kovalar, son çare market failsafe ile tamamlar; stop/TP'yi gerçek dolum fiyatından yeniden
  hesaplar. Amaç icra maliyetini (spread + kayma) düşürmek. Ancak bu, kurumların büyük yerleşiklerden hazır
  aldığı olgun bir kategori — bir startup için **cepheden rekabet zor**.
- **👥 Alıcı kitlesi (detay):** *Ekonomik alıcı:* Head of Trading. *Kullanıcı-şampiyon:* trader/execution desk.
  *Teknik onay:* CTO (FIX/venue bağlantısı). *Segment:* aktif işlem masaları. *Gerçekçi not:* TT/FlexTrade/Quod
  hâkim; ancak **varlık-özel veya küçük-broker niş** EMS'te yer olabilir — yine de bağımsız değil, suite'in gömülü icra modülü olarak.

### 7. **PositionKeeper** — OMS-lite Pozisyon Yaşam Döngüsü
- **Ne:** Pozisyon takibi, native+yazılım SL/TP yedeği, stale/trailing/rejim çıkışı, yetim-pozisyon uzlaştırma.
- **Sektör/alıcı:** TradingTech · küçük fon/broker.
- **ENDtrader'dan:** §9 pozisyon yönetimi & çıkışlar + yetim pozisyon koruması.
- **Katar/regülasyon:** Operasyonel; doğrudan kanca yok.
- **Rakip/zorluk:** OMS vendor'ları (Charles River, Bloomberg AIM) hâkim.
- **Bahis gücü:** ⭐⭐ (suite'in operasyon bileşeni olarak; tek başına zayıf).
- **🎯 Ne işe yarıyor (detay):** Açık pozisyonların **tek doğruluk kaynağını** tutar: borsadaki gerçek durumla
  iç kaydı sürekli karşılaştırır, tutarsızlıkları (yetim pozisyon, kaçak kapanış) yakalayıp uzlaştırır, native
  stop/TP'ye yazılımsal yedek sağlar ve otomatik çıkışları (stale/trailing/rejim) yönetir. "Sistemin sandığı
  pozisyon ile borsadaki gerçek pozisyon" farkından doğan operasyonel riski kapatır.
- **👥 Alıcı kitlesi (detay):** *Ekonomik alıcı:* COO / Head of Operations. *Kullanıcı-şampiyon:* ops /
  middle-office ekibi. *Teknik onay:* CTO. *Segment:* küçük-orta fon/broker (büyükler zaten Charles River/
  Bloomberg AIM kullanır). *Gerçekçi not:* tek başına OMS pazarına girmek zor; suite'in **operasyonel omurgası** olarak değerli.

---

## Özet Öncelik Sırası (bahis gücüne göre)

| Öncelik | Ürün | Küme | Ekonomik alıcı | Neden |
|---|---|---|---|---|
| 1 | **RiskFirewall** (2) | 🟢 | CRO/Head of Risk | En evrensel-zorunlu; kill-switch/limit her kurumda gerekir |
| 2 | **SurveilLog** (3) | 🟢 | CCO/MLRO | Katar için en iyi zamanlanmış (açıklanabilirlik zorunluluğu geliyor) |
| 3 | **OversightConsole** (9) | 🟢 | CRO/CCO | "Anlamlı insan gözetimi" zorunluluğuna birebir |
| 4 | **PreTrade Guard** (1) | 🟢 | Head of Trading/COO | Bundle çekirdeği; Şeriat-farkında geçit farkı |
| 5 | SizeWise (8) / EventShield (10) | 🟡 | Head of Risk | Küçük-firma nişi / suite eklentisi |
| 6 | RegimeIQ (5) | 🟡 | CIO/Head of PM | Tek başına zayıf, suite özelliği olarak güçlü |
| 7 | QuantLab (4) | 🔴→🟢 | Head of Quant/CIO | Tek başına dev-dolu; suite'te "test kanıtı" olarak değerli |
| 8 | ExecEngine (6) / PositionKeeper (7) | 🔴 | Head of Trading / COO | Yerleşik-dolu; yalnız gömülü modül |

**Tavsiye:** Tek ürün seçmek yerine **1+2+3+9 = "Algo-Governance & Surveillance Suite"** amiral gemisi;
5+8+10 suite özellikleri; 4 "test-before-deploy kanıtı" modülü; 6+7 gömülü. Kripto geliri (asıl ürün)
paralelde **BAE/Bahreyn**'de. Sonraki adım: bu amiral gemisi için tek-sayfalık ürün tanımı + QFTH pitch taslağı.

**Alıcı-kitlesi özeti (ortak örüntü):** RegTech/SupTech kümesinde **ekonomik alıcı uyum/risk yöneticisidir**
(CCO/MLRO/CRO), **teknik onay CTO/CISO'dur**, **kullanıcı uyum/gözetim analistidir** — yani satış "kâr vaadi"
değil **"regülatör karşısında koruma + denetim kolaylığı"** üzerine kurulur. TradingTech/Quant kümesinde alıcı
Head of Trading/Quant'tır ama orada yerleşikler güçlüdür. En temiz satış hikâyesi: **uyum/risk bütçesinden,
gelen QFMA regülasyonuna hazırlık gerekçesiyle.**
