# Muraqib — Algo-Governance & Surveillance Suite
### Ürün Pitch'i (bütüncül) · 14 Temmuz 2026

> **İsim notu:** *Muraqib* (Arapça: gözetmen/denetleyici) bir **yer-tutucudur**; alternatifler: *Helm*,
> *SentinelDesk*, *Aegis*. Ürün konumlandırması isimden bağımsızdır.
>
> **Dürüstlük notu:** Bu bir pitch'tir (ikna edici) ama abartısızdır. Regülasyon dayanağı **taslaktır**
> (yürürlükte değil) ve talep **saha-doğrulaması** ister; bu iki varsayım en sonda açıkça listelenmiştir.

---

## 1. Tek cümlede

> **Muraqib, lisanslı finans kurumlarının otomatik/algoritmik işlemlerini — gelen regülasyonun tam olarak
> isteyeceği biçimde — güvenle kontrol eden, kaydeden ve insan gözetimi altında tutan tek parça bir
> yazılım katmanıdır.** Kurum parasına dokunmaz, kimse adına işlem yapmaz; sadece işlemin *etrafındaki
> güvenlik ve denetim kabuğunu* sağlar.

---

## 2. Neden şimdi — problem ve zamanlama

Körfez, algoritmik işlemi **düzenlemeye başlıyor.** Katar Sermaye Piyasası Kurulu (**QFMA**) Mayıs 2025'te
bir taslak AI/algo düzenlemesi yayımladı; kapsamında **algoritmik işlem, gerçek-zamanlı izleme, test/denetim,
karar açıklanabilirliği ve "anlamlı insan gözetimi"** var ve fazlı olarak **2027'ye** kadar yürürlüğe girmesi
bekleniyor. QFC tarafında **QFCRA** zaten yetkili firmalardan "etkin sistem-kontrol ve risk yönetimi" istiyor.

Sonuç: yakın gelecekte otomatik işlem yapan **her lisanslı kurum**, elinde şu kanıtlarla olmak zorunda kalacak:
- işlem-öncesi risk kontrolleri ve acil durdurma (kill-switch),
- her kararın denetlenebilir kaydı ve açıklaması,
- gerçek-zamanlı gözetim ve insan onayı,
- devreye-almadan önce test edildiğinin belgesi.

**Ama** bu araçları bugün ya dev/pahalı yerleşiklerden (Bloomberg, Trading Technologies, SteelEye) alıyorlar,
ya da hiç ellerinde yok. Körfez'deki yeni ve orta ölçekli kurumlar için **hafif, algo-yerli, yerel-fiyatlı ve
İslami-finans-farkında** bir çözüm boşluğu var. **Muraqib bu boşluğu doldurur.** Regülasyon henüz taslakken
girmek = **erken-hareket avantajı** (kama).

---

## 3. Ürün — dört modül, tek kabuk

Muraqib, birbirini tamamlayan dört yeteneği **tek üründe** birleştirir. Hepsi kurumun stratejileri ile piyasa
(borsa/broker) arasında oturur:

```
   [Kurumun stratejileri / algoları]
                │
        ┌───────▼────────┐
        │    MURAQIB      │
        │ ┌────────────┐ │   1) Geçit  — kötü emri kaynakta durdur
        │ │ 1 PreTrade │ │   2) Fren   — canlı risk limiti + kill-switch
        │ │ 2 RiskFire │ │   3) Kayıt  — her kararın denetim izi + açıklaması
        │ │ 3 Surveil  │ │   4) Gözetim— tek ekrandan izle + insan onayı
        │ │ 4 Oversight│ │
        │ └────────────┘ │
        └───────┬────────┘
                │
        [Borsa / Broker / OMS]
```

1. **Geçit (PreTrade Guard):** Her emir borsaya gitmeden önce mandat/limit/piyasa-koşulu filtresinden geçer;
   uygunsuz emir kaynakta durur, gerekçeli kayıt bırakır.
2. **Fren (RiskFirewall):** Hesap-seviyesi canlı risk tavanları (günlük zarar, maruziyet, ardışık kayıp) +
   **tek tuşla acil durdurma**. Bir şey ters giderse saniyeler içinde durur.
3. **Kayıt (SurveilLog):** Her kararın ve reddin değiştirilemez, gerekçeli, zaman-damgalı kaydı; regülatöre-hazır
   yeniden-kurgu ve **"neden bu işlem yapıldı?" açıklaması**.
4. **Gözetim (OversightConsole):** Tüm hesap/stratejiyi tek ekrandan canlı izleme, alarm ve **kritik kararda
   insan-onay geçidi** — otomasyona insan gözü ve freni.

**Neden tek ürün?** Dördü de aynı motoru kullanır, aynı kişiye (uyum/risk) satılır ve birlikte "bütünsel bir
algo-güvenlik sistemi" oluşturur. Ayrı ayrı satmak hem müşteriyi yorar hem hikâyeyi zayıflatır.

---

## 4. Kime — alıcı ve satış hikâyesi

- **Ekonomik alıcı:** Uyum/Risk yöneticisi — **CCO (Chief Compliance Officer), MLRO veya CRO.**
- **Kullanıcı-şampiyon:** uyum/gözetim analisti, risk masası, iç denetim.
- **Teknik onay:** CTO/CISO (entegrasyon, değiştirilemez kayıt, veri-yerleşimi).
- **Firma segmenti:** aracı kurumlar, varlık yöneticileri, prop-desk'ler, piyasa yapıcılar (Katar'da 2025'te
  başladı), banka hazine/işlem masaları.

**Kritik nüans:** Bu ürün "sana para kazandırır" diye satılmaz — bu, kripto botunun DNA'sıydı ve kurumsalda
zayıftır. Muraqib **"seni regülatör karşısında korur ve denetimi kolaylaştırır"** diye satılır. Yani bütçesi
**trading kârından değil, uyum/risk bütçesinden** çıkar. Bu, hem daha savunmalı bir satın alma (korku/uyum
motivasyonu), hem de daha öngörülebilir bir bütçe kalemidir.

---

## 5. Neden biz — haksız avantaj

- **Motor 2 aydır sahada, çekişmeli koşullarda inşa edildi.** ENDtrader adlı çok-kullanıcılı işlem sisteminin
  çekirdeği: **fail-closed doğrulama** (hata/eksik veride "aç" değil "kapa"ya düşer), **her kararın gerekçeli
  loglanması**, çok-kiracılı gerçek-zamanlı izleme, backtest. Bunlar bir RegTech ürününün **en zor** parçaları
  ve **zaten ~%70 hazır.**
- **Kripto kökeni bir zayıflık değil, bir stres-testidir:** En düşmanca, en volatil, 7/24 piyasada çalışan bir
  risk/kontrol motoru, düzenli piyasalarda fazlasıyla dayanıklıdır.
- **Solo/çevik kurucu → hafif, hızlı, yerel-fiyatlı** — dev yerleşiklerin veremediği şey.

---

## 6. Neden Katar — giriş ve teşvikler

Ürünün **kripto olmaması** Katar'ın kapısını açar (kripto Katar'da yasaklı/dışlanmış; detay ayrı raporda).
Muraqib **regüle-olmayan bir B2B teknoloji** olduğu için:

- **QFC B2B FinTech lisansı** ile **%100 yabancı sahiplik + %100 kâr transferi** (finansal lisans gerekmez;
  hukukçu teyidiyle — parayı tutmaz, işlem yapmaz).
- **QFTH (Qatar FinTech Hub)** kuluçka/hızlandırma: para + mentör + **ekosisteme meşruiyet** (bankalara kapı açar).
- **Startup Qatar** teşvikleri: lisans/vize kolaylığı, sübvanse ofis, 5-yıllık girişimci ikamet, pazara giriş.
- **RegTech, Katar Ulusal FinTech Stratejisi'nin önceliği** — devletin gitmek istediği yönle birebir.

**Ama dürüst çerçeve:** Katar'daki fiili algo-trading alıcı havuzu **bugün küçük** (piyasa yapıcılık ancak
2025'te başladı). O yüzden doğru yapı: **Katar = teşvikli üs + regülatif hizalanma + ilk referanslar; satış =
GCC geneli** (BAE ve Suudi'nin buy-side ve algo sahnesi çok daha olgun). Kripto ürünü (asıl gelir) ise
paralelde **BAE/Bahreyn**'de lisanslanır. Yani: *Katar'da kur ve meşrulaş, komşuda ölçekle.*

---

## 7. İş modeli

- **B2B SaaS abonelik** — kurum başına yıllık lisans + modül/koltuk bazlı katman (Starter: Fren+Kayıt →
  Pro: +Geçit+Gözetim → Enterprise: on-prem/özel bulut, SLA).
- **Regüle-olmayan** → lisans yükü yok, sermaye şartı yok; gelir uyum bütçesinden.
- **Yapışkanlık:** denetim kaydı ve gözetim, sözleşmeyle-zorunlu ve göçü zor bir sistem → yüksek elde tutma.

---

## 8. MVP ve yol haritası

**Faz 0 — Kriptodan arındır (temel):** Bybit/kripto bağını bir adaptöre indir; çekirdeği varlık-bağımsız yap.
**Faz 1 — MVP (Fren + Kayıt):** Bir broker/OMS'i saran risk-limit + kill-switch servisi + değiştirilemez karar
günlüğü + basit gözetim dashboard'u; tek varlık sınıfı (hisse). Hedef: 1-2 **tasarım-ortağı** kurum.
**Faz 2 — Suite'i tamamla:** Geçit + insan-onay gözetimi; **FIX/OMS bağlayıcıları**, çok-varlık (sukuk/FX),
kurumsal kimlik (SSO/roller), açıklanabilirlik ekranı.
**Faz 3 — Regülasyon paketi:** QFMA/QFCRA raporlama şablonları, "test-before-deploy" kanıt modülü (QuantLab),
İslami-finans/Şeriat-farkında kural setleri, tokenize-varlık (QFC) hazırlığı.

---

## 9. Farklılaşma (neden yerleşikler değil de biz)

| | Yerleşikler (Bloomberg/TT/SteelEye) | **Muraqib** |
|---|---|---|
| Fiyat/ağırlık | Pahalı, ağır kurulum | Hafif, hızlı, yerel-fiyatlı |
| Odak | Genel/global | **Algo-yerli** (fail-closed doğrulama + karar loglama çekirdeği) |
| Yerellik | Sınırlı | Katar/GCC + **İslami-finans-farkında** + QFMA-şablonlu |
| Alıcı dostu | Kurumsal satış | Küçük-orta kuruma erişilebilir |

---

## 10. Dürüst riskler ve varsayımlar (pitch'in kırılgan yerleri)

1. **Regülasyon taslak** — QFMA düzenlemesi henüz yürürlükte değil; zamanlama/kapsam kayabilir. *(Azaltım:
   "gelen regülasyona hazırlık" olarak konumla, "mevcut zorunluluk" olarak değil.)*
2. **Katar pazarı küçük** — alıcı havuzu ince; tez GCC-geneli satışa dayanır. *(Azaltım: Katar'ı üs+referans, GCC'yi pazar yap.)*
3. **Kurumsal satış döngüsü uzun** — uyum/risk alıcısı yavaş karar verir. *(Azaltım: QFTH meşruiyeti + tasarım-ortağı ile referans.)*
4. **Perimetre hukuku** — "regüle değil" konumu ürün-özel; QFC/QFCRA hukukçusu teyidi şart (parayı tutan tek özellik bile regüle tarafa çeker).
5. **Talep doğrulanmadı** — konsept saha-testi (5-10 kurumla görüşme) yapılmadan büyük yatırım yapılmamalı.

---

## 11. İstenen (call to action)

- **QFTH/Startup Qatar'a:** kuluçka programına kabul + teşvik paketi + ilk kurumsal tanıştırmalar.
- **Tasarım-ortağı kurumlara:** MVP'yi birlikte pilotlayacak 1-2 broker/varlık yöneticisi.
- **Sonraki 90 gün:** Faz 0-1 MVP + 5-10 kurumla talep-doğrulama görüşmesi + QFC/QFCRA hukukçu teyidi.

> **Kapanış cümlesi:** Körfez algoritmik işlemi düzenlemeye başlıyor; kurumların yakında zorunlu olarak
> ihtiyaç duyacağı kontrol-kayıt-gözetim katmanının **en zor %70'i zaten inşa edildi.** Muraqib, o motoru
> kriptodan arındırıp doğru alıcıya (uyum/risk), doğru kapıdan (QFC/QFTH, regüle-olmayan), doğru zamanda
> (regülasyon gelmeden) sunar.
