# ML-Intern ➡️ NotebookLM Entegre Proje Ödevi

**Proje Adı:** Otonom Ajanlardan Sınıf Materyaline: Yapay Zekayla Uçtan Uca Ders Tasarımı

Bu ödevde amacımız; Antigravity yardımıyla kendi Gemini API anahtarınızı ML-Intern projesine bağlamak, otonom araştırma/veri analizi süreçlerini yönetmek ve elde edilen bilimsel çıktıları NotebookLM kullanarak veli/öğrenci dostu materyallere dönüştürmektir.

---

## 🛠️ 1. Aşama: Hazırlık (Antigravity ile API Bağlantısı ve Sunucuların Başlatılması)

Herhangi bir dosyayı elinizle düzenlemek veya terminale kod yazmak yerine, bu adımları doğrudan Antigravity sohbet ekranından talep edebilirsiniz. Daha önce ml-intern kurmuştuk sizin bilgisayarınıza. O dosya üzerinden ilerleyebilirsiniz.

### 🔑 Adım A: API Anahtarını Bağlatma
Antigravity sohbet ekranına kendi API anahtarınızı girerek şu komutu yazın:
👉 *"Bana ml-intern projesindeki .env dosyasını günceller misin? Gemini API anahtarım: [Kendi Gemini API Anahtarınız], MODEL_ID olarak da [Buraya son versiyon Gemini model kimliğini yazın - Örn: gemini/gemini-2.5-flash, gemini/gemini-3.1-pro vb. ] kullanmak istiyorum."*

*(Antigravity .env dosyasını arka planda sizin yerinize otomatik olarak düzenleyecektir.)*

### 🚀 Adım B: Projeyi Başlatma
Ayarlar tamamlandıktan sonra yine Antigravity'den sunucuları başlatmasını isteyin:
👉 *"Bana ml-intern projesinin backend ve frontend sunucularını arka planda çalışacak şekilde başlatır mısın?"*

*(Antigravity gerekli terminal komutlarını çalıştıracak ve tarayıcıdan giriş yapabileceğiniz http://localhost:3756 benzeri bir link verecektir.)*

---

## 🎯 2. Aşama: Otonom Madencilik (ML-Intern ile Veri Toplama)

Arayüze bağlandıktan sonra yapılacak işlemler:

### 📚 ML-Intern ile Otonom Literatür Taraması (Research Tool)
Bu görevde, ajanın akademik yayınları (arXiv ve Hugging Face Papers) tarama, metodoloji okuma ve karşılaştırmalı rapor hazırlama becerisini test edeceksiniz.

**ML-Intern Sohbet Kutusuna Yazılacak Örnek Komut (Kendi konunuza göre düzenleyebilirsiniz):**
> Ben uzman bir Montessori eğitimcisiyim. Dijital çağda Montessori pedagojisinin nasıl dönüştüğünü araştırmak istiyorum. Hugging Face Papers ve arXiv üzerinde 'Montessori pedagogy in digital age', 'active learning and digital materials', 'concrete vs abstract learning in AI era' konularında son 3 yılda yayınlanmış en önemli 3 akademik makaleyi otonom olarak araştır. Bu makalelerin metodolojilerini, veri setlerini incele. Sonrasında bu makalelerin Montessori ilkeleriyle çelişip çelişmediğini analiz eden, güçlü ve zayıf yönlerini ortaya koyan detaylı Türkçe bir karşılaştırmalı rapor hazırla.

### 📊 Hugging Face Veri Seti Analizi ve Soru Madenciliği
Bu görevde, ajanın veri setlerini inceleme (`hf_inspect_dataset`) ve bu verilerden yeni eğitim içeriği/soru üretme yeteneğini test edeceksiniz.

**ML-Intern Sohbet Kutusuna Yazılacak Örnek Komut:**
> Hugging Face Hub üzerinde okul öncesi veya erken çocukluk eğitimiyle ilgili (örneğin 'kindergarten', 'early-education', 'child-development' veya 'pedagogical-observation' etiketli) açık kaynak veri setlerini araştır. Bulduğun en zengin ve yapılandırılmış bir veri setini 'hf_inspect_dataset' aracını kullanarak incele. Veri setinde hangi sütunlar var, veri kalitesi nasıl, eksik veri oranları nelerdir analiz et. Bu veri setinin yapısından yola çıkarak, Montessori öğretmenlerinin sınıfta çocuk gözlemi yaparken dijital olarak nasıl bir gözlem/kayıt veri şeması oluşturabileceğini anlatan, veri odaklı detaylı Türkçe bir analiz raporu yaz.

---

## 📝 3. Aşama: Raporu Kaydetme

ML-Intern’in çalışma sonunda ürettiği rapor metnini veya soru havuzunu kopyalayın. Antigravity sohbet ekranına dönüp:
👉 *"Bana bu raporu ml-intern klasörünün içindeki REVIEW.md dosyasına kaydeder misin: [Kopyaladığınız Rapor Metni]"* komutunu verin.

---

## 🔄 4. Aşama: NotebookLM ile Eğitim Materyaline Dönüştürme

ML-Intern'in bulduğu akademik ve sayısal çıktıları, NotebookLM kullanarak sesli özet (podcast) ve sunum taslaklarına çevireceğiz.

1. **NotebookLM'e Giriş Yapın:** [notebooklm.google.com](https://notebooklm.google.com) adresinde yeni bir not defteri oluşturun.
2. **REVIEW.md Dosyasını Yükleyin:** Az önce Antigravity ile kaydettiğimiz `REVIEW.md` dosyasını kaynak (Source) olarak NotebookLM'e yükleyin.

### 🎧 Adım A (Akademik Podcast Üretimi)
* NotebookLM'in sağ üstündeki "Audio Overview" (Sesli Özet) kısmına gelin.
* **Customize (Özelleştir)** butonuna basarak şu Türkçe yönlendirmeyi yazın: *"Bu araştırmanın en can alıcı noktalarını bir öğretmenin ve velinin tartışacağı şekilde, sade bir dille özetleyin."* Ardından podcast'i üretin.

### 📊 Adım B (Veli / Öğrenci Sunumu Hazırlama)
* NotebookLM sohbet ekranına şu komutlardan seçtiğiniz konuya uygun olanını yazın: *"Yüklediğim bu araştırma raporuna dayanarak, velilere okulda yapay zekayı ve Montessori felsefesini nasıl harmanladığımızı anlatan 6 slaytlık bir veli bilgilendirme sunumu taslağı hazırlar mısın? Her slayt için başlık, 3 önemli bilgi maddesi ve görsel tavsiyesi ekle."*

---

## 📬 Ödev Teslim Etme

NotebookLM ekranının sağ üstündeki **"Share"** butonuna basarak defterinizi `coskun2mus@gmail.com` e-posta adresiyle paylaşın. Böylece otonom ajanın getirdiği veriler ile sizin hazırladığınız sunum ve sesli podcast çıktılarını tek bir panelden inceleyebiliriz.
