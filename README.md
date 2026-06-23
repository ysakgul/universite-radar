# TR Üniversite Radarı — Veri Seti

Bu klasör, [TR Üniversite Radarı]( ../ ) karşılaştırma aracında kullanılan ham ve derlenmiş sıralama verilerini içerir. Türkiye'deki üniversitelerin dört farklı sıralama sistemindeki bileşen (alt) puanlarını bir araya getirir.

> **Veri derleme tarihi:** 2026-06-21
> Tüm puanlar, ilgili sıralama kuruluşlarının **kamuya açık** kaynaklarından derlenmiştir.

## Klasördeki dosyalar

| Dosya | Açıklama |
|---|---|
| `rankings_master.json` | Tüm kaynakların **tam** birleşik veri seti (tüm üniversiteler, tüm yıllar). |
| `tool_data.json` | Aracın kullandığı **kırpılmış** sürüm (her yıl ilk ~25 + GTÜ; isimler tekilleştirilmiş). |
| `URAP_*.csv` | URAP yıllık Türkiye sıralaması ham tabloları. |
| `THE_*.csv` | Times Higher Education — Türkiye'deki üniversiteler (dünya sıralamasından filtreli). |
| `QS_*.csv` | QS World University Rankings — Türkiye'deki üniversiteler (filtreli). |
| `ARU_2025.csv`, `ARU_editions_history.csv` | YÖK Araştırma Üniversiteleri performans sıralaması. |

## Kaynaklar ve kapsam

### URAP — *University Ranking by Academic Performance*
- **Kapsam:** Türkiye sıralaması, tüm üniversiteler
- **Yıllar:** 2019-2020, 2020-2021, 2021-2022, 2022-2023, 2023-2024, 2024-2025, 2025-2026
- **Bileşenler:**

| Anahtar | Etiket |
|---|---|
| `article` | Makale |
| `citation` | Atıf |
| `total_document` | Toplam Bilimsel Doküman |
| `phd_score` | Doktora |
| `faculty` | Öğretim Üyesi |
| `international_collaboration` | Uluslararası İşbirliği |
| `domestic_collaboration` | Yurtiçi İşbirliği |
| `tubitak` | TÜBİTAK Projesi |
| `total` | Toplam Puan |

### THE — *Times Higher Education World University Rankings*
- **Kapsam:** Türkiye'deki üniversiteler (dünya sıralamasından filtreli)
- **Yıllar:** 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023, 2024, 2025, 2026
- **Bileşenler (0–100 mutlak ölçek):**

| Anahtar | Etiket |
|---|---|
| `scores_teaching` | Teaching |
| `scores_research` | Research Environment |
| `scores_citations` | Research Quality (Citations) |
| `scores_industry_income` | Industry |
| `scores_international_outlook` | International Outlook |
| `scores_overall` | Overall |

### QS — *QS World University Rankings*
- **Kapsam:** Türkiye'deki üniversiteler (dünya sıralamasından filtreli)
- **Yıllar:** 2021, 2022, 2023, 2024, 2025, 2026
- **Bileşenler (0–100 mutlak ölçek; yıllara göre metrik seti değişebilir):**

| Anahtar | Etiket |
|---|---|
| `Academic Reputation` | Akademik İtibar |
| `Citations per Faculty` | Öğr.Üyesi Başına Atıf |
| `Faculty Student Ratio` | Öğr.Üyesi/Öğrenci |
| `Employer Reputation` | İşveren İtibarı |
| `International Student Ratio` | Uluslararası Öğrenci |
| `International Faculty Ratio` | Uluslararası Öğr.Üyesi |
| `Employment Outcomes` | İstihdam Çıktıları |
| `International Research Network` | Uluslararası Araştırma Ağı |
| `Sustainability Score` | Sürdürülebilirlik |

### ARU — *YÖK Araştırma Üniversiteleri*
- **Etiket:** Araştırma Üniversiteleri (YÖK)
- **Kapsam:** YÖK 23 Araştırma Üniversitesi performans sıralaması
- **Yıllar:** 2025
- **Not:** 3-boyut kırılımı şu an yalnızca 2025 baskısı için açık veride mevcut.
- **Bileşenler (parantez içi azami puan):**

| Anahtar | Etiket |
|---|---|
| `kapasite` | Araştırma Kapasitesi (40) |
| `kalite` | Araştırma Kalitesi (40) |
| `isbirligi` | Etkileşim ve İş Birliği (20) |
| `total` | Toplam Puan (100) |

## Önemli notlar

- **Ölçek farkı:** THE ve QS bileşenleri 0–100 *mutlak* puandır. URAP ve ARU bileşenleri farklı aralıklardadır (ör. URAP'ta bir metrik 0–200, bir başkası 0–1150 olabilir). Bu yüzden araçta varsayılan görünüm, her ekseni o yılın en yükseğine göre %0–100'e normalize eder.
- **İsim tekilleştirme:** Aynı üniversite kaynaklara göre farklı yazılabiliyor (ör. GTÜ dört farklı isimle geçiyordu). `tool_data.json` içinde bu isimler tek bir kanonik kimliğe bağlanmıştır; `rankings_master.json` ise kaynaktaki orijinal isimleri korur.
- **Kırpma:** `tool_data.json` okunabilirlik için her indeks-yıl başına ilk ~25 üniversite + GTÜ ile sınırlandırılmıştır. Tam liste için `rankings_master.json` kullanılmalıdır.

## Kullanım ve haklar

Bu derleme akademik ve karşılaştırma amaçlıdır. Sıralama verilerinin telif ve tüm hakları ilgili yayıncı kuruluşlara (URAP, Times Higher Education, QS Quacquarelli Symonds, YÖK) aittir. Verileri kullanırken lütfen orijinal kaynağa atıf verin.


## Güncelleme — QS 2027 (Haziran 2026)

QS World University Rankings **2027** baskısı 18 Haziran 2026'da yayımlandı ve veri setine **tam olarak** eklendi: Türkiye'den 25 üniversite, 6 çekirdek QS göstergesi (Akademik İtibar, İşveren İtibarı, Öğr.Üyesi Başına Atıf, Öğr.Üyesi/Öğrenci, Uluslararası Öğrenci, Uluslararası Öğr.Üyesi), genel puan ve resmî sıra/bant ile. Kaynak: QS resmî verisinin kamuya açık dökümü; `data/QS_2027.csv`.

- GTÜ 2027: resmî bant **#851-900** (2025/26'da 1001-1200'dü) — net yükseliş. Öğr.Üyesi Başına Atıf 40.3 → 49.3, Akademik İtibar 7.0 → 9.1.
- QS 2027 WUR tablosu yalnızca 6 çekirdek göstergeyle yayımlandığından, "İstihdam Çıktıları", "Uluslararası Araştırma Ağı", "Sürdürülebilirlik" sütunları bu yıl için boştur; araç radarda bu eksenleri 2027'de otomatik gizler.

## Güncelleme — ARU sıralama trendi (çok yıllı)

YÖK Araştırma Üniversiteleri için boyut puanı kırılımı (kapasite/kalite/işbirliği) **yalnızca 2025 baskısında** kamuya açık tablo olarak var. Diğer baskılarda YÖK yalnızca sıralamayı açıkladı (2019 puanları sunum görselindeydi). Bu nedenle:

- Radar yalnızca **2025** için çalışır (tek tam yıl).
- **Sıralama trendi** için yayımlanan sıralı listeler eklendi: 2018 (ilk 5), 2019 (tam 16), 2022 (ilk 6), 2024 (ilk 6), 2025 (tam 23). Dosyalar: `data/ARU_2018.csv … ARU_2024.csv` (yalnızca sıra; puan sütunları boş = kamuya açık değil).
- GTÜ ARU sırası: 2019 **#10** → 2025 **#19**. Kohort büyüklüğü yıllara göre değiştiğinden (5/16/6/6/23) sıralar birebir kıyaslanamaz; araçta Trend sekmesinde uyarı gösterilir.

Kaynaklar: YÖK duyuruları ve basın (Hürriyet/AA/Memurlar.net). Boyut puanı içeren resmî YÖK tabloları (PDF/görsel) elde edilirse ilgili yıllar 2025 gibi tam eklenebilir.
