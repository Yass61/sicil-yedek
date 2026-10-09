# J3 — kanal ezgisi, üç yön keşfi (v14 J3 · 2026-09-25)

*`python muzik.py j3-gonder` üretti (A-C; D: `--yon D`). Kulak kontrolü ve yön seçimi **Yasin'de**. J4 (aile) başlatılmadı: **DUR**.*

**Ayarlar:**
- model `music_v2_5`;
- `prompt` + `force_instrumental: true`, 40 sn;
- `mp3_48000_128`;
- negatif üslup prompt metninde (hicaz dâhil).

**Model:** config `music_v1` diyordu; `music_v2_5` kullanıldı. Gerekçe: J4 seçilen denemenin song_id'sini `conditioning_ref` olarak kullanacak ve bu yalnız v2/v2_5'te var. v1 şarkısının v2_5'te referans olarak kabul edilip edilmediği dokümanda yazmıyor. Gerekçe `config/muzik.yaml`'da da yazılı.

**Dosyalar** `KAPI2_INCELEME/muzik/*.mp3`. Diskte duruyor, **depoya girmez** (`.gitignore`, videolarla aynı kural). Künye kayıtları `docs/muzik/kunye_defteri.jsonl`'de: model, istek, istek ve çıktı SHA-256, song_id, `kulak: bekliyor`, `telif_tarama: bekliyor`.

| Deneme | Yön | Süre | Seviye (ölçülen) | Tepe | song_id |
|---|---|---|---:|---:|---|
| J3-A-1 | A · Kâtip · Bûselik | 40,0 sn | −26,1 LUFS | −14,1 dBFS | `16HUUrh6PCG7USlAPwPR` |
| J3-A-2 | A | 40,0 | −12,7 | −1,2 | `0gq1BE21B5q6sdnQ5zeW` |
| J3-A-3 | A | 40,0 | −13,7 | −3,0 | `wElfrAphU6NHhRlFr6x7` |
| J3-B-1 | B · Gece · Nihâvend | 40,0 | −18,8 | −6,9 | `BZwkBGPYScbJabX31Gav` |
| J3-B-2 | B | 40,0 | −20,0 | −9,6 | `hJnGr8zkJetnBoO97zvd` |
| J3-B-3 | B | 40,0 | −15,1 | −1,2 | `dXDJa9FxPzWtSJfzGfdj` |
| J3-C-1 | C · Hikâye · Uşşak | 40,0 | −22,5 | −3,1 | `Ny6P1FIIaj43uNRCJgdx` |
| J3-C-2 | C | 40,0 | −16,5 | −3,5 | `wF555v4kqhxOFgh99bFD` |
| J3-C-3 | C | 40,0 | −21,2 | −1,5 | `jNw7B0LEFmMauV5yLmXb` |

- Seviye farkı büyük (−12,7 … −26,1 LUFS). Karışımda her parça yeniden normalize edilir; dinlerken ses düzeyini buna göre ayarla.
- Ölçülebilenlerin hepsi tamam: süre, sessiz olmama. **Vokal olup olmadığı ölçülmedi.** `force_instrumental` bunu garanti ettiğini söylüyor, ama kural kulak kontrolü.

## Kredi

| | Kredi |
|---|---:|
| Önce (kullanılan / limit) | 17.250 / 222.735 |
| Sonra (sayaç oturduktan sonra) | 22.200 / 222.735 |
| **J3 A-C harcaması** | **4.950** (6 dk → **825 kredi/dk**) |
| Tahmin (900 kredi/dk × 6 dk) | 5.400 |

🔴 **Düzeltme (aynı gün):** ilk sürümde "4.400 kredi, ~733/dk" yazdım. Sayaç üretimden hemen sonra okunmuştu; **gecikmeli işliyor.** Sonradan görünen +550 kredi başka bir kullanım değil, J3'ün geç işlenen kısmıydı; ilk sürümde bunu yanlış yere bağlamıştım. D koşusu aynı oranı verdi (825/dk). Oran tutarlı, sayaç oturmuş.

## Yasin'in geri bildirimi (2026-09-25) → yön D

- Genelde **2 numaralı denemeler** beğenildi, enstrüman sesi daha net. Ötekiler ağır.
- Tek sazlı, yavaş, tekdüze yapı **imza sesi için zayıf** bulundu.
- *Künyede `kulak` durumları değiştirilmedi. Vokal olup olmadığı bildirilmedi; `gecti` ya da `vokal` senin komutunla girer.*

## J3-D · "Taşra" (6 deneme)

**Ayarlar:**
- `music_v2_5`, `prompt` + `force_instrumental`, 40 sn.
- Tanbur ile bağlama diyaloğu: tanbur söyler, bağlama cevap verir, ikinci turda birlikte. Birkaç cümlede kaval ya da ney.
- Bendir ve def hafif ama belirgin nabız. Kısa, tekrar eden ezgi cümlesi. Melodi önde, zemin hafif; ağır alçak doku yok.
- **Negatif:** senin listen + **hicaz** (kanal kuralı).

| Deneme | Nabız | Seviye (ham) | song_id |
|---|---|---:|---|
| J3-D-1 | aksak 9/8, ağır zeybek adımı | −22,5 LUFS | `ogeIUkefc4fYjFREVjD4` |
| J3-D-2 | aksak | −21,4 | `H2dcl8NUTaPddkMpmRKu` |
| J3-D-3 | aksak | −19,7 | `qaGaid4FZ56sUn7jutFF` |
| J3-D-4 | düz ~92 BPM | −16,8 | `PsRJxDtwYeAyQVtaV2Mk` |
| J3-D-5 | düz | −16,3 | `bVCjE9KCUcEsglIYCwH1` |
| J3-D-6 | düz | −19,0 | `WQNMzvPuH1g6FCvQGsz9` |

**Kredi:** 22.200 → 25.500 = **3.300** (4 dk, 825/dk). Tahmin 3.600. Kalan **197.235**.

## Dinleme kopyaları — −16 LUFS

`KAPI2_INCELEME/muzik/dinleme/`: 15 parçanın hepsi, A-C'ler de dahil ki eşit seviyede kıyaslanabilsin. Çalma listesi `J3_dinleme_16LUFS.m3u`.
- **Yöntem:** ölçülen farka göre **sabit kazanç** + yalnız tepelere sınırlayıcı (−1,5 dBFS).
- loudnorm'un iki geçişli kipi burada doğrusal kalamadı, dinamik kipe düşüp parçaları sıkıştırıyordu. Dinamik değişmesin diye kullanılmadı.
- **Ölçülen sonuç:** hepsi **−16,0 … −16,2 LUFS**, tepe ≤ −1,6 dBFS. Kazançlar: A-1 +10,4 dB … A-2 −3,0 dB.
- Ham dosyalar değişmedi. Kopyalar yalnız dinleme içindir, künye kaydı taşımaz.

## J4 için ders (Yasin)

Aile parçalarında da **melodi net, zemin hafif**; ağır, alçak dokudan kaçın. Bu `config/muzik.yaml → j4`'e not olarak yazıldı.

## Senin adımın — kulak kontrolü ve yön seçimi

Her deneme için bir satır:

```
python muzik.py kulak J3-A-1 gecti      # ya da: vokal  → yeniden üretim kuyruğa girer
```

Sonra bir yön seç: A, B ya da C, ve referans olacak deneme. J4 (10 parçalık aile) o denemenin song_id'siyle kurulur. **Ben başlatmıyorum.**

---

# KANAL TEMASI — son tur (Yasin, 2026-09-25)

## Kulak kararları (künye defterine işlendi)

| Deneme | Karar | Not |
|---|---|---|
| **J3-D-4** | **gecti** | birinci tercih; tema referansı |
| J3-D-3 | gecti | beğenildi (aksak renk) |
| J3-D-1, D-2, D-5, D-6 | **ret** | beğenilmedi. Yeni `ret` sonucu: vokal değil, yeniden üretim kuyruğa **girmez** |

## Dört deneme (R1-R4)

**Ayarlar:**
- `music_v2_5`, `composition_plan`, 30 sn.
- Her chunk'ta ses referansı **J3-D-4** (`conditioning_ref`, 0-30 sn, `condition_strength: medium`).

| Bölüm | Süre | Yönerge |
|---|---|---|
| Motif | 0-6 sn | tanbur tek başına, 4-7 notalık sade motif, 6. saniyede net çözülüş |
| Cevap | 6-14 sn | def adımı girer (~96 BPM, orta frekans), bağlama cevap verir |
| Birlikte | 14-24 sn | tanbur ve bağlama birlikte; bir iki cümlede kaval ya da ney |
| Kapanış | 24-30 sn | tanbura dönüş, net kapanış notası |

- **Nabız:** R1, R2 düz yürüyüş (D-4 hissi). R3, R4 düz nabız + her cümle sonunda kısa aksak vurgu (D-3 rengi).
- **Negatif:** senin listen + hicaz (kanal kuralı) + "deep low drone", "heavy sub bass" (senin "derin alçak zemin yok" yönergen).

**İki teknik not:**
1. 🔴 **Söz riski kapatıldı.** API'ye göre composition_plan'daki `text` **şarkı sözü satırı** olarak okunabiliyor.
   - `text`'e yalnız `[bölüm adı]` ve `{yönerge}` girdi; tarif `positive_styles`'ta.
   - `j4_dogrula` bunun dışındaki metni artık BLOK ediyor.
   - Henüz koşmamış J4 kurucusunda aynı risk vardı (açıklama düz metindi); o da düzeltildi.
2. **Referans sınırı:** API ses referansını **en çok 30 sn** kabul ediyor.
   - İlk gönderim (0-40 sn) 422 ile reddedildi. Döngü ilk hatada durdu, **kredi harcanmadı**.
   - Sınır dokümanda yazmıyordu; artık istek gitmeden BLOK.

| Deneme | Nabız | Süre | Seviye (ham) | song_id |
|---|---|---:|---:|---|
| TEMA-R1 | düz | 30,0 sn | −19,0 LUFS | `XOuAxUyZs7wujtNZ9cM0` |
| TEMA-R2 | düz | 30,0 | −19,8 | `pMmTLhvrJio1rYqJDJhr` |
| TEMA-R3 | aksak vurgu | 30,0 | −19,0 | `tCo44cNcGBhTvuRVVX3C` |
| TEMA-R4 | aksak vurgu | 30,0 | −20,1 | `EPZLwjxJK73Gv4f3k9E1` |

## Jenerik kesitleri

- Her denemenin ilk 6 saniyesi `KAPI2_INCELEME/muzik/TEMA-Rn_jenerik6.mp3`.
- Kesikte tık olmasın diye son 30 ms'de doğrusal rampa var (D3 kuralı). Bu bir sönme değil.
- **Kendi başına bitip bitmediği senin kulak kontrolünde.**

## Dinleme kopyaları

- `KAPI2_INCELEME/muzik/dinleme/TEMA_dinleme_16LUFS.m3u`: her deneme, ardından kendi jenerik kesiti. Sırayla R1 … R4.
- Sabit kazanç + tepe sınırlayıcı. Ölçülen: hepsi **−16,0 … −16,1 LUFS**, tepe ≤ −1,5 dBFS.
- Depo dışı.

## Kredi ve aylık 62 dakikalık hak

| | Kredi |
|---|---:|
| Önce | 25.500 / 222.735 |
| Hemen sonra (sayaç oturmamış) | 26.736 |
| **Oturduktan sonra** | **27.148** |
| **Tema turu harcaması** | **1.648** (2 dk → 824/dk; J3'teki 825 ile aynı oran) |
| Reddedilen ilk gönderim (422) | 0 |
| **Kalan** | **195.587** |

**62 dk müzik hakkı:**
- API bu hakkı göstermiyor; abonelik yanıtında dakika alanı yok. Hesap bizim üretim kayıtlarımızdan.
- Bu dönemde (yenilenme 2 Ekim) üretilen müzik: J3 A-C **6:00** + J3-D **4:00** + tema **2:00** = **12:00 dk**. Kalan **~50 dk**.
- Jenerik kesitleri ve dinleme kopyaları yerel kesim; hak yemez.
- Hesabın başka yerden (web arayüzü) kullanımı bu sayıya **dahil değil**.

## Sıradaki (Yasin seçince)

1. Tema kilitlenir.
2. Köprüler, bölüm sonu ve fragman sürümü o temadan türetilir (J4, "melodi net, zemin hafif" dersiyle).
3. Kanal açılınca gizli yüklemeyle telif eşleşme testi yapılır (`muzik.py telif`, v15 A1).

**DUR.**

---

# KANAL İMZASI — nihai tur "Etnotronik + nefes" (Yasin, 2026-09-25)

*Görev metni `docs/gorevler/v16_imza.md`. Sohbetteki "E serisi", "Gerilim" ve "Etnotronik" komutları uygulanmadı; bu tur onların yerine geçti. Bu komutlar hiç bana ulaşmamıştı.*

## 0 · Kulak kaydı

- TEMA-R1…R4: **ret** ("tek düze, imza sesi değil").
- J3-A-2, B-2, C-2: **gecti**, bölüm içi yatak olarak kalır.

## 1 · Müzik — G1-G6

**Ayarlar:**
- `music_v2_5`, `composition_plan`, 30 sn, **referans ses yok**. Promptta sanatçı ya da eser adı yok.
- 🔴 **API kısıtı:** chunk en kısa 3 sn. "0-2 sn giriş" ve "22-24 sn durma" tek başına chunk olamadı. Yapı 4 chunk'a (6 / 8 / 8 / 8 sn) sığdırıldı; giriş vuruşu ve ani durma chunk içinde `{yönerge}` olarak yazıldı.

| Deneme | İstenen | **Ölçülen tempo** | **Ani durma (22-24 sn)** | Sesin sonu | Seviye (ham → dinleme) |
|---|---|---:|---|---:|---|
| G1 | bağlama, 4/4, ~104 BPM | **~113** | ölçülmedi: sessizlik yok | 28,5 sn | → −16,2 LUFS |
| G2 | bağlama, 4/4, ~110 BPM | **~125** (band dışı) | yok | 28,1 sn | → −16,0 |
| G3 | kemençe, 4/4, ~106 BPM | ~104 | yok (24,7'de **bitiyor**; motif son kez gelmiyor) | 24,7 sn | → −16,2 |
| G4 | kemençe, 4/4, ~112 BPM | ~112 | yok | 26,4 sn | → −16,0 |
| G5 | bağlama, aksak 9/8, ~105 BPM | ~104 | yok | 28,3 sn | → −16,0 |
| G6 | ney + kemençe, 100 → 115 yükseliş | ~115 (6-22 sn ortalaması) | yok | 26,0 sn | → −16,0 |

- 🔴 **Model "ani durma" yönergesine uymadı.** Hiçbir denemede 20-26 sn arasında, arkasından ses gelen bir sessizlik yok. Ölçüt: 6-20 sn ortancasının 20 dB altı, kesintisiz. Müzik kesilmedi; durma istenirse kurguda yapılabilir, ya da yeniden üretilir.
- **Tempo:** G1 ve G2 istenenin belirgin üstünde. Ölçüm, 6-22 sn arasındaki vuruş zarfının otokorelasyonu (`muzik_katman.py`, sentetik 107 BPM'de 107,1 buldu). Gerçek müzikte yanılabilir: **TAHMİN**, kulakla doğrulanmalı.
- **Jenerik kesitleri:** `IMZA-Gn_jenerik6.mp3`, ilk 6 sn, sonda 30 ms tık önleyici rampa.

| Deneme | song_id |
|---|---|
| G1 | `lZHfddILYokevmKtyOOy` |
| G2 | `dHQAbePrLI79qQJyNyev` |
| G3 | `RdFl4W7a68G9rt1BMvE1` |
| G4 | `wiZQzhy6fdYyYpxXlt8t` |
| G5 | `wOeCjEIW9Oo6Rwztt4dA` |
| G6 | `vv4Egs7rvV2MGYCitOny` |

## 2 · Nefes katmanı ve arşiv sesleri — ElevenLabs ses efektleri

- `eleven_text_to_sound_v2`, Beta değil.
- Her metne "No words, no singing, no humming, no vocal tone, no chanting" eklendi.
- `muzik.py` dinî sözleri (zikir, ezan, ilahi…) BLOK ediyor.
  - İlk sürümde "single" sözcüğünün içindeki "sing" sahte alarm verdi; artık sözcük sınırıyla aranıyor.
- Nefes döngüleri: `NEFES-100` (4,80 sn) · `NEFES-105` (4,57) · `NEFES-110` (4,36) · `NEFES-115` (4,17), 8'er vuruş, `loop`. Ayrıca `NEFES-DERIN` (2,5 sn).
- **Arşiv sesleri de burada üretildi:** `ARSIV-MUHUR` (tek kuru darbe), `ARSIV-KAGIT` (çıngırak gibi hışırtı), `ARSIV-KALEM` (kamış kalem cızırtısı, döngü).
  - Gerekçe: diskteki `varliklar/ses/foley` dosyalarının kaynağı ve lisansı hiçbir yerde kayıtlı değil; mühür sesi de yoktu. İmza kanal kimliği olduğu için lisansı bilinmeyen malzeme kullanılmadı.
- İlk gönderim 422 aldı (ses efektinde `mp3_48000_*` yok), kredi 0. `mp3_44100_128` kullanıldı.

## 3 · Kural

`bolumler/SENARYO_KURALLARI.md` MÜZİK + `config/ses_tasarimi.yaml → anakronizm`: dinî sözler (zikir, ezan, ilahi) kullanılmaz; **sözsüz nefes ritmi serbest**.

## 4 · Dinleme paketi — `dinleme/IMZA_dinleme_16LUFS.m3u` (18 parça, hepsi −16 LUFS)

- Altı deneme + her birinin 6 sn'lik jenerik kesiti.
- **Katmanlı örnekler:** G1 ve G3, `muzik_katman.py`. Olaylar **ölçülen** vuruş ızgarasına oturuyor.

| Sürüm | İçerik |
|---|---|
| **a** yalnız müzik | — |
| **b** + arşiv | mühür darbesi ölçü başlarında (6 sn → durma) ve kapanışta · kâğıt hışırtısı iki vuruşta bir · kamış kalem cızırtısı doku (2 sn → durma) |
| **c** + arşiv + nefes | nefes 6. sn'de girer, vuruşa oturur (en yakın döngü ölçülen tempoya uyduruldu: G1 → 115, G3 → 105) · 14-22 sn arasında yarım vuruş kaydırılmış ikinci kat (sıklaşma) · durmada tek derin nefes |

- ⚠ Model durma üretmediği için "durma" **nominal 22,0 sn**'ye kondu. Müzik o anda susmuyor; yalnız katmanlar susuyor, derin nefes giriyor.
- Katmanlar ölçüldü (c − a fark sinyali): 0-6 sn ihmal edilebilir (−54 / −67 dB) · 6-14 sn −29 / −23 dB · 14-22 sn −28 / −21 dB. Nefes girişi ve sıklaşma yerinde.
- Başka bir denemeyi seçersen: `python muzik_katman.py IMZA-Gn`.

## 5 · Künye

Künye defterine 6 müzik + 8 ses efekti kaydı. Her kayıtta:
- model, plan (Creator), üretim tarihi;
- istek (composition_plan ya da ses efekti metni);
- Beta notu;
- istek ve çıktı SHA-256, song_id (müzik);
- `kulak` ve `telif_tarama`: bekliyor.

## 6 · Kredi ve 62 dakikalık hak

| | Kredi |
|---|---:|
| Önce | 27.148 |
| İmza müziği sonrası (oturmuş) | 29.620 → **müzik 2.472** (3 dk, 824/dk; önceki turlarla aynı oran) |
| Ses efektleri sonrası | 29.922 → **ses efekti 302** (8 üretim, 27,4 sn) |
| Reddedilen ilk ses efekti gönderimi (422) | 0 |
| **Kalan** | **192.813** |

⚠ **Ses efekti maliyeti şüpheli düşük.** İki okuma aynı çıktı (302), ama iki resmî rakamın ikisinden de çok az:
- fiyat sayfası 200 kredi/üretim → 1.600;
- doküman 40 kredi/sn → 1.096.

Ya sayaç yine gecikiyor (J3-D'de ilk okuma 550, oturmuş değer 3.300'dü) ya da ses efektleri farklı ücretleniyor. **Kesin değil:** bir sonraki `python muzik.py j2` okumasıyla doğrulanmalı. B9 maliyet tablosu bu yüzden değiştirilmedi.

**62 dk müzik hakkı** (bizim üretimimiz, bu dönem):

| Tur | Süre |
|---|---:|
| J3 A-C | 6:00 |
| J3-D | 4:00 |
| Tema | 2:00 |
| **İmza** | **3:00** |
| **Toplam** | **15:00** |
| **Kalan** | **~47 dk** |

Ses efektleri müzik hakkından düşmez. Web arayüzü kullanımı dahil değil.

**DUR.** Seçim Yasin'de. Seçilen denemeye katmanlar uygulanır; kanal açılınca gizli yüklemeyle telif testi yapılır.

---

# KANAL İMZASI — H serisi (2026-09-25)

*Görev: Yasin, 2026-09-25. G serisi reddedildi. Teşhis: saniye saniye `composition_plan` modelde boşluk ve seyreklik üretiyor. Beğenilen J3 ve D serileri basit istemle üretilmişti.*

🔴 **Kural** (imza için, bundan sonra): `composition_plan` kullanılmaz. Basit, betimleyici istem + `force_instrumental`; uzun üret, iyi anı montajda kes.
- `config/muzik.yaml` → `imza_h`.
- `muzik.py imza-h-gonder`: `imza_h_dogrula` bir plan eklenirse BLOK verir.

## 0 · Kulak kaydı

IMZA-G1…G6 → **ret**. Not: "boş giriş, seyrek vuruş, melodi zayıf". Künye defterinde işli.

## 1 · Üretim — music_v2_5, 60 sn, prompt + force_instrumental

- Her istemde Yasin'in ortak cümlesi birebir var. Ardından kısa negatifler geliyor: no choir, no belly dance, no wedding or festive feel, no EDM drop, no epic brass, no hijaz. "No vocals" ortak cümlede.
- Sanatçı ya da eser adı yok.

⚠ **H1/H2'nin ses referansı uygulanamadı.**
- API, J3-D4 ses referansını (`conditioning_ref`) **yalnız `composition_plan` içinde** kabul ediyor. `prompt` ile birlikte verilemiyor (api-reference/music/compose, 2026-09-25).
- Kural önde tutuldu: H1/H2 **referanssız** üretildi. D-4'ün sazları ve havası istemde sözle betimlendi: tanbur-bağlama diyaloğu, ama daha enerjik; sık çerçeve davulu, bağlama tezenesi, kemençe ezgisi.
- Referans şart ise tek yol tek chunk'lık bir plan: 60 sn, bir betimleyici yönerge, D-4'ün 0-30 sn'si, `force_instrumental` yok. **Karar Yasin'in.**

## 2 · Otomatik ön kontrol — `muzik_kesit.py`

- **Düşme ölçütleri:**
  - ilk 1 sn'nin RMS'i −40 dBFS'in ya da ortancanın 15 dB altında;
  - ortancanın 25 dB altında 1,5 sn'den uzun kesintisiz bölge var (son 3 sn sayılmaz).
- **Kalibrasyon, üretimden önce eski parçalarla:**
  - G2-G6 düşüyor (2,6-6,8 sn boşluk).
  - J3-D-4 ve D-3 geçiyor.
  - 🔴 **G1 geçiyor** (en uzun boşluk 1,1 sn). Seyrek vuruşun altında süren ses, seviyenin boşluk eşiğine inmesini engelliyor.
  - Bu ölçüt "boş giriş"i yakalıyor, "seyrek vuruş"u yakalayamıyor.
  - Vuruş yoğunluğu ölçüsü denendi: G1 ile D-4'ü ayırmadı (10,9 ve 10,0 vuruş/sn). Yanıltıcı olacağı için eklenmedi.

| Deneme | İlk 1 sn | Ortanca | En uzun boşluk | Sonuç |
|---|---:|---:|---:|---|
| H1 | −14,9 dBFS | −12,7 | 0,40 sn | ✅ geçti |
| H2 | −10,8 | −14,2 | 0,00 | ✅ geçti |
| H3 | −10,6 | −14,5 | 0,85 | ✅ geçti |
| **H4** | **−57,5** | −17,4 | **1,85** (0,00-1,85) | ❌ **düştü**: boş giriş + boşluk → bir kez yeniden üretildi |
| H4-2 | −12,9 | −11,4 | 0,00 | ✅ geçti |
| H5 | −17,2 | −20,2 | 0,00 | ✅ geçti |
| H6 | −14,9 | −15,8 | 0,55 | ✅ geçti |

→ **Altı denemenin altısı dinlemeye geçti.** H4 ikinci üretimle geçti. Elenen yok.

## 3 · Kesit önerisi (sezgisel, kulak kararı DEĞİL)

- **Tempo** ölçüldü: vuruş zarfının otokorelasyonu.
- **Faz:** zarfın vuruş ızgarasına en iyi oturduğu kaydırma. Ölçü = 4 vuruş. Adaylar **yalnız ölçü başları**.
- **Puan:**
  - ½ tüm-bant enerjisi + ½ ezgi bandı (400-2500 Hz);
  - − 20 × sessiz kare payı;
  - \+ ezgi girişi (kesit başı ile öncesi arasındaki fark; 6 sn'de ağırlık 1, 30 sn'de ½).

| Deneme | Ölçülen tempo | İstenen | 30 sn kesit başı | 6 sn kesit başı |
|---|---:|---:|---:|---:|
| H1 | 95,1 BPM | ~104 | 0,39 sn | 0,39 sn |
| H2 | 108,0 | ~108 | 0,02 | 0,02 |
| H3 | 103,6 | ~104 | 9,72 | 9,72 |
| H4-2 | 107,8 | ~108 | 27,22 | 47,27 |
| H5 | 100,0 | ~100 | 19,23 | 19,23 |
| H6 | 103,7 | ~104 | 23,14 | 23,14 |

- H1 ve H2'de iki kesit de parçanın başında. Bu parçalar ilk saniyede tam başladığı için öyle çıktı. Ölçütün başlangıç lehine bir eğilimi olabilir; **kulakla bakılmalı.**
- H1 istenenden yavaş (95 BPM). Tempo her zamanki gibi istemden değil, ölçümden okunuyor.

## 4 · Dinleme paketi — `dinleme/IMZA_H_dinleme_16LUFS.m3u`

- 18 parça: her deneme için sırayla 6 sn kesit, 30 sn kesit ve 60 sn tam hâl.
- Hepsi −16 LUFS (−16,0 ile −16,2 arası; tepe −1,6 ile −7,2 dBFS arası), sabit kazanç + tepe sınırlayıcı.
- Kesitlerde 20 ms açılış, 6 sn'de 300 ms, 30 sn'de 1 sn kapanış yumuşatması var.

## 5 · Künye

- `docs/muzik/kunye_defteri.jsonl`: H1, H2, H3, H4-2, H5, H6 → kulak **bekliyor**.
- H4 → **ret** ("otomatik ön kontrol: boş giriş …").
- Her kayıtta istek ve çıktı SHA-256'sı, song_id ve ön kontrol ölçümü var. Tam ölçümler `imza_h_olcumleri.json`.

## 6 · Kredi ve 62 dakikalık hak

| | Kredi |
|---|---:|
| Önce | 29.922 |
| Sonra (iki okuma aynı) | 35.697 → **müzik 5.775** (7 üretim × 1 dk = 825/dk; önceki turlarla aynı) |
| **Kalan** | **187.038** / 222.735 |

- ✅ **Ses efekti tutarı doğrulandı: 302.** Sayaç imza turundan sonra saatlerce 29.922'de kaldı. Resmî rakamların altında, ama gerçek.

**62 dk müzik hakkı** (bizim üretimimiz, bu dönem):

| Tur | Süre |
|---|---:|
| J3 A-C | 6:00 |
| J3-D | 4:00 |
| Tema | 2:00 |
| İmza G | 3:00 |
| **İmza H** | **7:00** (6 + H4 tekrarı) |
| **Toplam** | **22:00** |
| **Kalan** | **~40 dk** |

**DUR.** Kulak ve seçim Yasin'de. H1/H2 referans kararı da Yasin'de (§1).

---

# BÖLÜM İÇİ YATAKLAR — J4 (v17 D1, 2026-09-25)

- **Yöntem** (Yasin): seçilen J3 denemesi (A-2 Bûselik, B-2 Nihâvend, C-2 Uşşak) **ses referansı**. `composition_plan` tek chunk, 120 sn; referans 0-30 sn, `condition_strength: medium`.
- `force_instrumental` bu yolda yok. Negatiflerde vocals, singing, choir, voice ve humming var; `j4_dogrula` her birini denetliyor.
- İstem: melodi net, zemin hafif ve arkada, anlatının altında; döngüye uygun (giriş büyümesi yok, final kadansı yok, sessizlik yok).
- **Araç:** `muzik.py yatak-gonder` · `config/muzik.yaml → yatak`. Ölçümler `yatak_olcumleri.json`.
- 🔴 "İmzada composition_plan kullanılmaz" kuralı **yalnız imza** içindir; yataklar Yasin'in tarifine göre referanslı plan.

## Otomatik ön kontrol (imza H ile aynı ölçüt) — düşen BİR kez yeniden üretildi

| Yatak | İşlev | Referans | 1. üretim | 2. üretim | Sonuç |
|---|---|---|---|---|---|
| YATAK-A | bağlam ve usul | J3-A-2 | ❌ boş giriş (ilk sn −61 dBFS), 2,0 sn boşluk | ❌ boş giriş (ilk sn −46 dBFS) | **ELENDİ** |
| YATAK-B | gerilim | J3-B-2 | ❌ boşluk 100,1-101,9 sn | ❌ boşluk 113,2-117,0 sn (sönüm) | **ELENDİ** |
| YATAK-C | ifade ve kapanış | J3-C-2 | ✅ geçti (ilk sn −25,2, en uzun boşluk 0,45 sn) | — | **dinlemede** |
| YATAK-UYKU | uyku arşivi | J3-C-2 | ✅ geçti (ilk sn −24,4, boşluk 0,65 sn) | — | **dinlemede** |

**Dinleme kopyaları:** `dinleme/YATAK-C_16LUFS.mp3`, `dinleme/YATAK-UYKU_16LUFS.mp3` (−16,0 LUFS; tepe −4,4 / −2,6 dBFS).

⚠ **Elenenlerin gövdesi kurtarılabilir** (Yasin'in kararı):
- A-2'nin sorunu yalnız ilk ~1 sn: model referansın başındaki sessiz girişi taşıyor.
- B-2'nin sorunu son ~7 sn (sönüm).
- İkisi de 2-110 sn gibi bir kesitle kural içine girer. Kesim $0; istenirse dinleme kopyası üretilir.
- Yeniden üretim ~1.650 kredi / 2 dk.

⚠ **Döngü:** dört yatak da sonda sönüyor. Baş/son 2 sn seviyesi: C −19,4 / −43,7 dB, UYKU −20,8 / −57,4 dB. "Final kadansı yok" talimatı tutmadı. Montajda döngü kesiti ve çapraz geçiş gerekecek; kesit önerisi `muzik_kesit` ile yapılabilir.

## Kulak

`docs/muzik/kunye_defteri.jsonl`:
- YATAK-C ve YATAK-UYKU → kulak **bekliyor**.
- A, A-2, B, B-2 → **ret** (otomatik ön kontrol).

## Kredi ve 62 dakikalık hak

| | Kredi |
|---|---:|
| Önce | 35.697 |
| Sonra | 45.597 → **müzik 9.900** (6 üretim × 2 dk = 825/dk) |
| **Kalan** | **177.138** / 222.735 |

- Ses efekti bu turda yok (toplam 302, doğrulanmış).
- **62 dk müzik hakkı:** önceki 22:00 + yataklar **12:00** = **34:00** kullanıldı → **~28 dk kalan**.

**DUR.** Kulak Yasin'de. D2 (Suno) dosyalar gelince; D3 imza seçimini bekliyor.
