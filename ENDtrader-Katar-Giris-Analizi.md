# ENDtrader V4 × Katar — Pazara Giriş / Teşvik Uygunluk Analizi
### Regülasyon-öncelikli, güven-etiketli, dürüst değerlendirme

**Ürün:** ENDtrader V4 — çok kullanıcılı, rejim-adaptif **Bybit USDT Perpetual (kripto vadeli) otomatik
işlem botu** (SOP v2 doğrulama, risk kalkanları, backtest, Gemini rejim seçici). Kaynak: `v4sistemdokumantasyonu.md`.
**Soru:** Bu ürünü Katar pazarına Startup Qatar / QFTH / QFC teşvikleriyle nasıl sokabiliriz, nasıl
konumlandırmalı/sunmalıyız? **Bağlam:** ~2 aydır geliştirilen olgun ürün; solo/yabancı kurucu.
**Rapor tarihi:** 14 Temmuz 2026.

---

## ⚠️ ÖNCE OKUYUN

Bu ortamın egress politikası birincil siteleri (qcb.gov.qa, qfc.qa, qfcra.com) 403 ile engelledi;
bulgular ≥2–3 bağımsız arama-ekstresi + **QFCRA'nın kendi duyurusunun** özeti temelinde "Yüksek (tavanlı)"
seviyesine taşındı. **Nihai yatırım/kuruluş kararı öncesi bir QFC/QFCRA hukukçusuyla teyit şart.**

> **Tek cümlelik sonuç:** ENDtrader **mevcut kripto-vadeli-bot** halinde Katar teşviklerine **uymuyor**
> (kripto Katar'da yasaklı/dışlanmış + üçüncü-taraf oto-işlem regüle + Şeriat uyumsuz). Değerli olan
> **motor teknolojisidir**; Katar'a giriş ancak motoru **kriptodan arındırılmış, lisanslı kurumlara
> satılan B2B icra/risk altyapısı** olarak yeniden konumlandırınca mümkün. Kripto işini gerçekten
> yapacaksanız doğru GCC üssü **BAE (ADGM/VARA) veya Bahreyn (CBB)** — Katar değil.

---

## 1. Ürünün Regülatif Kimliği — Katar Nasıl Görür?

Ürün, mühendislik olarak güçlü (çok-katmanlı doğrulama, fail-closed risk, backtest). Ama regülatör
mühendisliğe değil **fiili faaliyete** bakar. Katar'ın gözünde ürün üç "kırmızı" nitelik taşır:

| Nitelik | Kaynak (dokümandan) | Katar'daki sorun |
|---|---|---|
| **Kripto varlık** | Bybit USDT Perpetual | QCB yasağı + QFC "Excluded Token" |
| **Kaldıraçlı türev** | 10x varsayılan, perpetual futures | Perakende türev + Şeriat (riba/maysir/gharar) |
| **Üçüncü-taraf adına otomatik icra** | çok kullanıcılı, kullanıcı API anahtarıyla emir | "Asset/money management" = QFCRA regüle faaliyet |

Yani ürün, Katar regülasyonunun **en hassas üç kategorisinin kesişiminde** duruyor. Bu, "regüle-olmayan
enabler" kapısını (önceki fintech raporundaki kolay yol) da kapatır: çünkü yazılımın **amacı** dışlanmış
bir faaliyettir.

---

## 2. Regülasyon Duvarı — Üç Katman + Şeriat

### Katman 1 — Kripto yasağı (QCB)
QCB **2018/6 sayılı Genelge**, Katar'daki tüm finansal kurumların kripto işlem yapmasını **yasakladı.**
2026 itibarıyla Katar'da **lisanslı hiçbir kripto borsası/venue yok.** [Güven: Yüksek (tavanlı)]

### Katman 2 — QFC kriptoyu açıkça dışlıyor (2024)
**QFC Dijital Varlık Çerçevesi 2024** (Eyl 2024): gerçek-dünya varlıklarının **tokenizasyonuna** (hisse,
bono, **sukuk**) izin verir — **ama kripto paralar ve stablecoin'ler "Excluded Tokens" (Madde 9/2) olarak
DIŞLANMIŞTIR.** QFCRA bunu ayrı bir duyuruyla teyit etti. Yani "QFC'nin yeni dijital varlık rejimi bizi
kapsar" **denemez** — tam tersine, çerçeve kriptoyu ismen dışarıda bırakır. [Güven: Yüksek (tavanlı) —
QFCRA birincil duyurusu ekstresi]

### Katman 3 — Üçüncü-taraf oto-işlem = regüle faaliyet (QFCRA)
QFC'de **"money and asset management business, investment business"** regüle faaliyettir ve **QFCRA
yetkisi** ister. Kullanıcı adına emir yürüten çok-kullanıcılı bot, büyük olasılıkla bu kapsama girer;
algoritmik işlem QFCRA'nın piyasa-suistimali kurallarında da açıkça anılır. Kripto için bu yetki
verilmeyeceğinden **regüle kapı da kapalıdır.** [Güven: Orta–Yüksek]

### Şeriat katmanı (soft ama belirleyici)
Kaldıraçlı perpetual + funding rate (≈**riba**) + yüksek spekülasyon (**maysir/gharar**) → yaygın fıkhî
görüşe göre **Şeriat-uyumsuz.** İslami finansın **ulusal fintech stratejisinde çapraz tema** olduğu bir
ülkede bu, teşvik jürisi ve kurumsal alıcı nezdinde ciddi bir olumsuz sinyaldir. [Güven: Orta]

---

## 3. Karar: Mevcut Ürün ↔ Teşvik Uygunluğu

| Teşvik/Program | Mevcut kripto-bot uygunluğu | Neden |
|---|---|---|
| Startup Qatar Investment Program (START/GROW) | ❌ | Öncelik sektör "FinTech" ama kripto faaliyeti yasaklı; jüri regülatif fizibiliteyi sorar |
| QFTH Incubator/Accelerator | ❌ | QCB/QDB ekosistemi; kripto-türev perakende otomasyonu kabul edilmez |
| QCB Regulatory/Express Sandbox | ❌ | Sandbox, *lisanslanabilir* yeniliği test eder; kripto dışlanmış |
| QFC B2B FinTech lisansı (regüle-olmayan) | ⚠️ Ancak **kriptodan arındırılırsa** | Yazılımın amacı dışlanmış faaliyet olduğu sürece riskli |
| QFC Dijital Varlık / Tokenizasyon rejimi | ⚠️ Sadece **tokenize varlığa pivot** edilirse | Kripto hariç; RWA/sukuk tokenizasyonu açık |

**Özet:** Ürünü *olduğu gibi* sunmak bir seçenek değil. Katar için soru **"motorun hangi kısmı,
kriptodan arındırılıp lisanslı bir çerçeveye oturtulabilir?"**

---

## 4. Yeniden Konumlandırma Yolları (dürüst artı/eksi)

Değerli IP kripto değil; **rejim-adaptif icra + çok-katmanlı doğrulama (SOP) + fail-closed risk motoru +
backtest altyapısı.** Bu motor varlık-sınıfından bağımsızdır. Dört yol:

### Yol A — B2B "İcra & Risk Altyapısı" (ÖNERİLEN)
Motoru kriptodan ayır; **lisanslı kurumlara (broker, varlık yöneticisi, banka) satılan white-label
teknoloji** olarak konumla: SOP doğrulama katmanları + risk kalkanları + backtest + rejim tespiti.
*Sen işlem yürütmezsin, müşteri parasına dokunmazsın* → **QFC B2B FinTech lisansı (regüle-olmayan), %100
yabancı sahiplik.** Varlık sınıfı: Katar-legal (hisse, sukuk, emtia, FX, tokenize RWA).
**+** Önceki fintech raporundaki enabler kapısıyla birebir uyumlu; strateji temasıyla (RegTech/altyapı) örtüşür.
**−** Perakende kripto cazibesini kaybedersin; kurumsal satış döngüsü uzun; "yatırım tavsiyesi/araf’a
sokma" sınırından titizlikle uzak durmalısın. **[Fizibilite: Orta–Yüksek]**

### Yol B — Tokenize Varlık / RWA İcra Katmanı
QFC'nin **tek açık dijital-varlık alanı** tokenizasyon (Digital Assets Lab, sukuk/hisse tokenizasyonu).
Motoru tokenize menkul kıymet icra/piyasa-yapıcılığına uyarla.
**+** Katar'ın *aktif istediği* alan; yüksek stratejik hizalanma; az rakip.
**−** Pazar henüz emekleme aşamasında; ürün önemli ölçüde yeniden inşa; muhtemelen yine regüle taraf. **[Fizibilite: Orta]**

### Yol C — Şeriat-Uyumlu Algoritmik Altyapı
Kaldıraç/short/perpetual/funding'i çıkar; helal enstrümana (Şeriat-taranmış spot hisse, sukuk) uyarla.
İslami fintech ulusal öncelik.
**+** Güçlü diferansiyatör; teşvik jürisine ve kurumsal alıcıya olumlu sinyal.
**−** Stratejinin çekirdeği (kaldıraçlı türev alfa) değişir; ürünün kimliği baştan tasarlanır. **[Fizibilite: Orta]**

### Yol D — Katar sadece ÜS, müşteri offshore (kripto legal pazarlar)
QFC %100 sahiplik + ikamet + teşviklerden yararlan; müşteriler kriptonun legal olduğu ülkelerde.
**+** Ürüne en az dokunuş.
**−** Katar'dan *kripto-türev işi işletmek* bile QFC/QCB kurallarını ihlal edebilir (mutlaka hukukçu);
Startup Qatar "Katar'a ekonomik katkı" ister — offshore-kripto bunu zayıf karşılar; itibar/Şeriat sürtünmesi.
**Yüksek regülatif risk; teşvik pitch'i zayıf. [Fizibilite: Düşük–Orta]**

---

## 5. Eğer Kripto İşi *Asıl* Hedefse — Doğru GCC Kapısı Katar Değil

Bu, önceki sigorta raporunun sonucuyla aynı örüntü ("Katar'ı sonraya bırak"):

- **BAE:** ADGM (FSRA) ve Dubai **VARA** — GCC'nin en olgun sanal-varlık lisans rejimleri; kripto türev/aracılık lisanslanabilir.
- **Bahreyn:** CBB'nin **Crypto-Asset Module**'ü — bölgede erken ve işleyen bir çerçeve.
- **Katar:** Kripto için **kapalı**; tokenizasyon için açık ama kripto-türev değil.

**Strateji:** Kripto ürününü BAE/Bahreyn'de lisansla; Katar'a *ancak* Yol A/B/C ile (kriptosuz, kurumsal/tokenize/Şeriat) gir.

---

## 6. Yol A'yı Seçersen — Somut Giriş Planı

1. **Ürün ayrıştırması:** Motoru "asset-class-agnostic execution & risk engine" olarak paketle; Bybit/kripto
   bağını bir adaptör katmanına indir (Katar sunumunda görünmez).
2. **Konumlandırma cümlesi:** *"Lisanslı finans kurumları için rejim-adaptif, çok-katmanlı doğrulamalı
   algoritmik icra ve risk-yönetimi altyapısı"* — "kripto trading bot" **denmez.**
3. **Tüzel yapı:** QFC B2B FinTech lisansı, %100 yabancı sahiplik; ilk müşteri = lisanslı kurum.
4. **Perimetre disiplini:** parayı tutma, tavsiye verme, kendi adına icra etme — yalnız kuruma *araç* sağla.
5. **Program:** QFTH Incubator'a *bu kurumsal altyapı* tezi + Şeriat/tokenizasyon açısıyla başvur; olgunlaşınca Startup Qatar START.
6. **Hukuk:** başvurudan önce bir QFC/QFCRA hukukçusuyla "regüle mi?" testini yaptır (tek bir icra özelliği bile regüle tarafa çeker).

**Söylenecek:** kurumsal altyapı, risk yönetimi, RegTech, Şeriat-uyum, tokenizasyon-hazır.
**Söylenmeyecek:** Bybit, perpetual, kaldıraç, "kullanıcılar için otomatik kâr", perakende kripto.

---

## 6.1 "Kurumsal Algoritmik İcra & Risk Altyapısı" — Bileşen Haritası

**Ana içgörü:** ENDtrader, bir kripto botu olarak yazılırken aslında lisanslı kurumların **yönetişim/risk
yükümlülüklerine denk düşen** bir algo-kontrol katmanı inşa etti. Pivot = bu makineyi son-kullanıcıdan
alıp **lisanslı kurumun altına kontrol katmanı** olarak koymak. Sen parayı tutmaz/işlem yapmazsın →
**regüle değilsin** (QFC B2B FinTech lisansı, hukukçu teyidiyle). Alıcı: algo/otomasyon koşan lisanslı kurum.

**Tablo okuma anahtarı — iki ayrı güven:** *(a) Bileşen* = sizin dokümanınızdan, **Yüksek**. *(b) Katar
regülasyon kancası* = 3. doğrulama turunda atfı düzeltilmiş; **QFMA taslağı (2025, fazlı→2027)** ve
**QFCRA CTRL 2020 (yürürlükte, genel)** temelli. Detay + pazar uyarısı tablonun altında.

| # | Bileşen (sende var — **Yüksek güven**) | Kurumsal karşılığı | Katar regülasyon kancası (doğru atıf) | Kanca güveni |
|---|---|---|---|---|
| 1 | SOP v2 — 3 katman doğrulama (fail-closed, gerekçeli ret) §5 | İşlem-öncesi doğrulama / sinyal geçidi | QFMA taslak: algo sistem testi/denetimi + manipülasyon önleme | Orta *(taslak)* |
| 2 | Risk kalkanları + acil durdurma (fail-closed) §6 | İşlem-öncesi risk limitleri + **kill-switch** | QFCRA CTRL 2020: "etkin sistem-kontrol + risk yönetimi" *(yürürlükte, genel)*; QFMA taslak: gerçek-zamanlı izleme | **Orta-Yüksek** *(genel)* / Orta *(algo-özel, taslak)* |
| 3 | Karar log'u (`v3_decision_log` + heartbeat) §2,11 | Denetim izi / karar günlüğü + açıklanabilirlik | QFMA taslak: izleme+test+denetim, **karar kriterlerinin ifşası**; QFCRA: bağımsız denetim | Orta |
| 4 | Backtest + optimizer (dinamik komisyon/kayma) §12 | Devreye-alma öncesi test/simülasyon | QFMA taslak: algo'nun **devreye-alma öncesi test/validasyonu** | Orta *(taslak)* |
| 5 | Rejim tespiti (ATR/ADX/Hurst + AI) §3 | Piyasa-durumu analitiği | *Doğrudan kanca yok — ürün özelliği* | — |
| 6 | İcra (maker-chase, limit TP, failsafe) §8 | Akıllı emir icrası / execution algo | QSE Millennium (LSEG) + 2025'te başlayan piyasa yapıcılık; algo/DMA sahnesi **emekleme** | Düşük-Orta *(nascent)* |
| 7 | Pozisyon yaşam döngüsü + çıkışlar §9 | Otomatik pozisyon & çıkış yönetimi | *Operasyonel; doğrudan kanca yok* | — |
| 8 | Boyutlandırma & kaldıraç motoru §7 | Pozisyon boyutlandırma / sermaye tahsisi | QFCRA CTRL: risk yönetimi sistemleri *(genel)* | Orta |
| 9 | Çok-kiracılı + şifreli anahtar + dashboard/uyarı §2,11 | Kontrol paneli + gerçek-zamanlı izleme/alarm | QFMA taslak: gerçek-zamanlı izleme + **"anlamlı insan gözetimi"** | Orta |
| 10 | Haber/takvim kalkanı §6 | Olay-riski kontrolleri | *Operasyonel risk; dolaylı* | Düşük-Orta |

**En keskin tek ürün — "Algo-Trading Yönetişim & Risk Katmanı" (RegTech):** yukarıdaki satır 1+2+3+4+9+10.
RegTech Katar önceliği; en zor kısımlar (%~70) zaten hazır. Varlık sınıfı: hisse, sukuk, FX, tokenize RWA
(kripto DEĞİL).

> ### 🔎 Doğrulama turu 3 (14 Tem) — regülasyon güçlendi, TALEP zayıf
> **Düzeltme geçmişi:** İlk taslakta "QFCRA algo kuralları bunu **zorunlu tutar**" (⭐) demiştim; 2. turda
> bunun ABD/AB kaynaklı (FINRA/MiFID II RTS 6) olduğunu, Katar mevzuatı olmadığını kabul ettim. 3. tur
> resmi netleştirdi:
>
> **Regülasyon tarafı — GÜÇLENDİ [Orta-Yüksek]:**
> - **QFMA taslak AI düzenlemesi (Mayıs 2025)** artık çok sayıda ciddi hukuk kaynağıyla (Sultan Al-Abdulla
>   & Partners, Mondaq, Charles Russell Speechlys, QNA resmî) doğrulandı: **algoritmik işlem** kapsamı +
>   **gerçek-zamanlı izleme** + **test/denetim** + **açıklanabilirlik** + **"anlamlı insan gözetimi"**;
>   fazlı uygulama **2027'ye kadar.** Ama hâlâ **taslak** — yürürlükte değil.
> - **QFCRA CTRL 2020**: yetkili firmalar "etkin sistem-kontrol + risk yönetimi" tutmak **zorunda**
>   (yürürlükte, ama genel — algo-özel değil).
> - **Doğru çerçeve:** "bugün sert zorunluluk" DEĞİL → **"2025-2027'de gelen regülasyona erken hazırlık"**
>   (zamanlama/erken-hareket avantajı gerçek).
>
> **Talep/pazar tarafı — ZAYIF [asıl risk]:**
> - Katar'da **algo-trading sahnesi emekleme aşamasında:** piyasa yapıcılık ancak **2025'te** başladı
>   (1 Ekim 2025, Wasata → tek hisse Mekdam); DMA/algo kuralına dair belge yok.
> - QFC'de 2.489 firma (2024) var ama çoğu fintech/danışmanlık/IT; **fiilen algo koşan alıcı havuzu çok küçük.**
> - **Sonuç:** Ürün regülasyona uygun, ama **Katar tek başına pazar olarak ince.** Bu, "sadece Katar" tezini
>   zayıflatır; **rasyonel yapı: Katar = teşvikli üs + regülatif hizalanma, satış = GCC geneli** (BAE/Suudi
>   buy-side ve algo/DMA sahnesi çok daha olgun). Karar öncesi QFMA/QFCRA + QSE + birkaç broker ile saha doğrulaması şart.

**Boşluklar (dürüst):** bugün kripto/Bybit'e bağlı → çok-varlık + kurumsal venue/OMS/**FIX** bağlayıcıları,
kurumsal kimlik (SSO/roller), SLA, on-prem/özel bulut gerekir. "Retail-kâr botu" DNA'sı → "kurumun stratejisini
güvenle koşturan araç" DNA'sına geçmeli. Pazar küçük (az lisanslı kurum) → BAE'yi paralel değerlendir.

---

## 7. Kaynaklar

- [QFCRA — Kripto/stablecoin "Excluded Tokens" duyurusu](https://www.qfcra.com/news/qfc-regulatory-authority-clarifies-that-cryptocurrencies-stablecoins-and-certain-other-virtual-assets-are-excluded-tokens-under-the-new-digital-assets-framework/)
- [QFC — Digital Assets Framework 2024](https://www.qfc.qa/en/media-centre/news/list/qatar-financial-centre-issues-qfc-digital-assets-framework-2024)
- [Forbes — Qatar 2024 Digital Assets Regulations ilk bakış](https://www.forbes.com/sites/digital-assets/2024/10/16/a-first-look-at-qatars-2024-digital-assets-regulations/)
- [Charltons Quantum — Qatar dijital varlık regülasyonu genel bakış](https://charltonsquantum.com/digital-asset-regulations-in-qatar/)
- [The Block — QFC crypto trading ban](https://www.theblock.co/linked/52087/qatar-bans-crypto-trading-report)
- [Lightspark — Is Crypto Legal in Qatar? (2026)](https://www.lightspark.com/knowledge/is-crypto-legal-in-qatar)
- [Library of Congress — GCC kripto regülasyonu (Katar)](https://blogs.loc.gov/law/2025/01/regulation-of-cryptocurrencies-in-the-gulf-cooperation-council-gcc-countries-part-two/)
- [QFCRA — Regulated Activities](https://www.qfcra.com/regulated-activities/)
- [QFCRA Rulebook — Regulated Activities Part 1](https://qfcra-en.thomsonreuters.com/rulebook/part-1-activities-which-subject-provided-regulations-shall-be-regulated-activities)
- [Charles Russell Speechlys — Qatar market conduct / algoritmik işlem](https://www.charlesrussellspeechlys.com/en/insights/expert-insights/corporate/2025/defining-market-boundaries-qatar-codifies-financial-market-conduct/)
- [QFC — What We License (B2B FinTech)](https://www.qfc.qa/en/registering-a-company/what-we-license)
- [FINRA — Algorithmic Trading (ABD; pre-trade kontrol/kill-switch bağlamı — Katar değil, analoji)](https://www.finra.org/rules-guidance/key-topics/algorithmic-trading)
- [Kroll — Algorithmic Trading under MiFID II (RTS 6; AB — analoji)](https://www.kroll.com/en/publications/financial-compliance-regulation/algorithmic-trading-under-mifid-ii)
- [QFMA taslak AI düzenlemesi — Sultan Al-Abdulla & Partners (hukuk)](https://qatarlaw.com/news/the-qatar-financial-markets-authority-announces-draft-regulations-on-artificial-intelligence-use)
- [QFMA taslak AI düzenlemesi — Mondaq (hukuk)](https://www.mondaq.com/financial-services/1630606/the-qatar-financial-markets-authority-announces-draft-regulations-on-artificial-intelligence-use)
- [QNA resmî — QFMA AI düzenlemesi "yakında" (12 May 2025)](https://qna.org.qa/en/news/news-details?id=qfma-official-to-qna-draft-regulation-on-ai-use-in-financial-market-to-be-issued-soon&date=12/05/2025)
- [Charles Russell Speechlys — Qatar piyasa davranışı kodifikasyonu (algo dahil)](https://www.charlesrussellspeechlys.com/en/insights/expert-insights/corporate/2025/defining-market-boundaries-qatar-codifies-financial-market-conduct/)
- [QFCRA — Governance & Controlled Functions (CTRL) / sistem-kontrol yükümlülüğü](https://www.qfcra.com/governance-and-controlled-functions/)
- [QFCRA — Rules for Authorised Firms](https://www.qfcra.com/rules-for-authorised-firms/)
- [The Peninsula — QFC'de 2024'te 800+ yeni firma, toplam 2.489](https://thepeninsulaqatar.com/article/29/01/2025/over-800-new-firms-registered-with-qatar-financial-center-in-2024-recording-156-growth)
- [QSE piyasa yapıcılık / likidite sağlayıcı (2025 başlangıcı) bağlamı](https://algotradinglib.com/en/pedia/q/qatar_stock_exchange_(qse).html)
- İlgili: bu depodaki `Startup-Qatar-Fintech-Giris-Raporu.md` (teşvik kapıları) ve `Katar-Sigorta-Firsat-Raporu.md` ("Katar'ı sonraya bırak" örüntüsü).

---

## 8. Sınırlar ve Sonraki Adımlar

- **Kanıt tavanı:** primary sayfalar 403; QFCRA duyurusu dahil ekstreler tutarlı ama birincil belge açılmadı. **Hukukçu teyidi şart.**
- **"Üçüncü-taraf oto-işlem regüle mi?"** sorusunun ürün-özel cevabı QFCRA görüşüyle netleşmeli (Orta güven).
- **Karar noktası kurucuya ait:** (a) motoru kriptodan ayırıp Katar'a kurumsal altyapı olarak mı gireceksin
  (Yol A), yoksa (b) kripto ürününü BAE/Bahreyn'de mi lisanslayacaksın? İkisi paralel de yürüyebilir:
  **kripto geliri BAE/Bahreyn'de, kurumsal/tokenize altyapı Katar'da.**
- Yol A seçilirse: 1 sayfalık "asset-class-agnostic execution infra" tek-sayfa (one-pager) + QFTH başvuru taslağı çıkarılabilir.
