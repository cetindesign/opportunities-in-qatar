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
- İlgili: bu depodaki `Startup-Qatar-Fintech-Giris-Raporu.md` (teşvik kapıları) ve `Katar-Sigorta-Firsat-Raporu.md` ("Katar'ı sonraya bırak" örüntüsü).

---

## 8. Sınırlar ve Sonraki Adımlar

- **Kanıt tavanı:** primary sayfalar 403; QFCRA duyurusu dahil ekstreler tutarlı ama birincil belge açılmadı. **Hukukçu teyidi şart.**
- **"Üçüncü-taraf oto-işlem regüle mi?"** sorusunun ürün-özel cevabı QFCRA görüşüyle netleşmeli (Orta güven).
- **Karar noktası kurucuya ait:** (a) motoru kriptodan ayırıp Katar'a kurumsal altyapı olarak mı gireceksin
  (Yol A), yoksa (b) kripto ürününü BAE/Bahreyn'de mi lisanslayacaksın? İkisi paralel de yürüyebilir:
  **kripto geliri BAE/Bahreyn'de, kurumsal/tokenize altyapı Katar'da.**
- Yol A seçilirse: 1 sayfalık "asset-class-agnostic execution infra" tek-sayfa (one-pager) + QFTH başvuru taslağı çıkarılabilir.
