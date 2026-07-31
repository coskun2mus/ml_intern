# 📓 NotebookLM Öğretmen Rehberi
> Tarih: 2026-05-21 | Proje: EduAI Assistant / İstekler

---

## Giriş

NotebookLM, Google'ın geliştirdiği, yüklenen belge ve PDF'leri analiz eden yapay zeka destekli bir araştırma ve not alma asistanıdır.
Öğretmenler için PDF ders kitabı, ders notu veya herhangi bir materyali yükleyip özel bir asistan gibi kullanabilirler.

🔗 **Başlangıç linki:** https://notebooklm.google.com  
*(Google hesabıyla ücretsiz, PDF'i sürükle bırak yeter.)*

---

## 1. 🎧 Sesli Kitap Oluşturma (Audio Overview)

NotebookLM'in en güçlü özelliklerinden biri **"Audio Overview"** fonksiyonudur.

### Adımlar:
1. NotebookLM'e kitabı (PDF veya metni) yükle
2. Sağ panelde **"Audio Overview"** butonuna tıkla
3. İki yapay zeka sesi (erkek + kadın) podcast formatında kitabı **tartışıyor** ve özetini sunuyor
4. **İndir** → MP3 olarak kaydedebilirsin

> ⚠️ **Not:** Türkçe PDF'lerde şu an **İngilizce sesle** üretiyor. Türkçe ses desteği beta aşamasında.

---

## 2. 🎵 Kitaba Şarkı Yapma

NotebookLM bunu doğrudan yapamaz — ancak şu akış etkili çalışıyor:

### Önerilen İş Akışı:
1. NotebookLM'e kitabı yükle
2. Şu prompt'u sohbet kutusuna yaz:
   > *"Bu kitabın ana temasını, çocuklar için uyaklı ve tekrarlı bir şarkı sözüne dönüştür. Nakarat + 2 kıta olsun."*
3. Çıkan metni al → **Suno.ai** veya **Udio.com**'a yapıştır → gerçek şarkıya dönüştür

### Faydalı Araçlar:
- https://suno.com — Türkçe metin girip şarkı üretebilirsin
- https://www.udio.com — Alternatif AI müzik üretici

---

## 3. ❓ Akılcı Soru Seti Oluşturma

Bu, NotebookLM'in **en güçlü olduğu alan**dır.

### Adımlar:
1. PDF'i NotebookLM'e yükle
2. Sohbet kutusuna aşağıdaki prompt'lardan birini yaz:

### Hazır Prompt'lar:

```
"Bu kitaba göre 10 adet çoktan seçmeli soru üret, cevaplarıyla birlikte."
```

```
"Bloom taksonomisinin analiz ve değerlendirme basamaklarına göre açık uçlu sorular üret."
```

```
"Bu kitabı hiç okumamış bir öğrenci için ön bilgi yoklama soruları yaz."
```

```
"Bu konunun en sık yanlış anlaşılan 5 noktasını bul ve bunlara yönelik düzeltici sorular oluştur."
```

3. Sonuçları kopyala → **Google Forms** veya **Word** belgene yapıştır

---

## 4. 📊 İnfografik İçin NotebookLM Kullanımı

NotebookLM infografiği çizmez, ancak **içerik iskeletini** hazırlar.

### İş Akışı:
1. PDF'i yükle
2. Şu prompt'u yaz:
   > *"Bu kitabın ana kavramlarını hiyerarşik bir outline olarak listele: Başlık, alt başlık, 3 anahtar bilgi formatında."*
3. Çıkan yapıyı → **Canva** veya **Napkin.ai**'ye götür → otomatik infografik oluştur

### İnfografik Hazırlarken Sorulacak Sorular (NotebookLM'e):
```
"Hangi veriler görselleştirilmeli?"
"Okuyucu için en kafa karıştırıcı konsept hangisi?"
"Bu konudaki temel istatistikler veya rakamlar nelerdir?"
```

### Faydalı Araçlar:
- https://napkin.ai — Metni otomatik infografiğe çevirir
- https://canva.com — Sürükle bırak infografik şablonları

---

## 5. 📓 Öğretmenler NotebookLM'i Nasıl Kullanabilir?

### Temel İş Akışı:

```
PDF / Kitap / Ders Notu yükle
        ↓
Özel asistan gibi sorular sor
        ↓
Ders planı / özet / soru seti çıkar
        ↓
Audio Overview ile podcast üret
```

### Pratik Kullanım Senaryoları:

| Senaryo | NotebookLM'e Yazılacak Prompt |
|---|---|
| **Ders planı** | *"Bu konuyu 40 dakikalık ders planına çevir, giriş/gelişme/sonuç yapısıyla"* |
| **Veli mektubu** | *"Bu üniteden ne öğrendiklerini velilere açıklayan kısa bir mektup yaz"* |
| **Farklılaştırma** | *"Aynı konuyu 3 farklı seviye için anlat: başlangıç, orta, ileri"* |
| **Özet çıkarma** | *"Bu kitabın sadece öğretmen için okuyacağı 1 sayfalık özetini yaz"* |
| **Kaynak önerisi** | *"Bu kitabın desteklediği konular için ek kaynak ve etkinlik öner"* |
| **Sınıf tartışması** | *"Bu konuyu sınıfta tartışmak için 5 açık uçlu tartışma sorusu üret"* |

### Özel Eğitim Prompt'ları (Hazır Kopyala-Yapıştır):

```
"Bu kitabı 7 yaş grubu için anlaşılır bir dille özetle."
```

```
"Bu ünitedeki anahtar kelimeleri ve tanımlarını bir sözlük formatında listele."
```

```
"Bu konuyu öğretirken yapılan en yaygın pedagojik hatalar nelerdir?"
```

```
"Bu materyal için Montessori yaklaşımına uygun 3 etkinlik öner."
```

---

## 📌 Notlar ve Sınırlamalar

| Özellik | Durum |
|---|---|
| Türkçe PDF analizi | ✅ Çalışıyor |
| Türkçe Audio Overview | ⚠️ Beta (İngilizce üretiyor) |
| Görsel/fotoğraf yükleme | ✅ Destekleniyor |
| YouTube linki yükleme | ✅ Destekleniyor |
| Web sayfası yükleme | ✅ Destekleniyor |
| Şarkı/müzik üretme | ❌ Desteklenmiyor (Suno.ai kullan) |
| İnfografik çizme | ❌ Desteklenmiyor (Napkin.ai kullan) |
| Maksimum kaynak sayısı | 50 kaynak / notebook |

---

*Son güncelleme: 2026-05-21*
