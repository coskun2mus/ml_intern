ML Intern: Kapsamlı Proje Rehberi
1. Nedir ve Ne Amaçla Kullanılır?
ML Intern, Hugging Face smolagents ekibi tarafından Nisan 2026'da yayınlanan açık kaynak, otonom ML mühendislik ajanıdır. Şu görevleri kendi kendine yapabilir:

📚 Literatür taraması (paper arama, okuma, atıf grafikleri)
💻 Eğitim/inference kodu yazma ve çalıştırma
🚀 Hugging Face Jobs üzerinde GPU eğitimi başlatma
📊 Dataset ve model doğrulama
🔄 Model Hub'a push etme
Temel felsefe: "Literatürden başla, dokümantasyona güvenme, kodunu doğrula."

2. GitHub Repo vs Web Kullanımı Arasındaki Farklar
Özellik	GitHub/CLI	Web (HF Space)
Kurulum	git clone + uv sync + .env dosyası	Tarayıcıya git, HF OAuth ile giriş
URL	github.com/huggingface/ml-intern	huggingface.co/spaces/smolagents/ml-intern
Model seçimi	LiteLLM üzerinden herhangi bir model (Claude, GPT, Ollama, vLLM...)	Kısıtlı liste: Ücretsiz (Kimi, MiniMax, GLM, DeepSeek) / Pro (Claude, GPT)
Kimlik doğrulama	.env dosyasındaki API anahtarları	Hugging Face OAuth
Sandbox	Yerel subprocess veya kendi HF Space sandbox'ın	HF Space sandbox (paylaşımlı)
İzleme (traces)	{kullanıcı}/ml-intern-sessions dataset'i (özel)	Aynı dataset, OAuth üzerinden
Bildirimler	Slack gateway desteği	Belirtilmemiş
Geliştirme	Tam kaynak kod erişimi	Sadece tüketici arayüzü
Özet: GitHub repo geliştiriciler ve güç kullanıcılar için; web arayüzü hızlı deneme veya API anahtarı olmayanlar için.

3. Mimari ve Ana Bileşenler
Yüksek Seviye Akış
Kullanıcı Girdisi → submission_loop → Agent Loop (max 300 iterasyon)
    ↓
LLM çağrısı (LiteLLM) → Tool çağrıları ayrıştırma → Onay kontrolü
    ↓
ToolRouter (19 araç) → Sonuçları ContextManager'a ekle → Tekrarla
Ana Bileşenler
Bileşen	Dosya	Amaç
Agent Döngüsü	agent/core/agent_loop.py	Ana döngü, LLM çağrıları, onay sistemi
Oturum Yönetimi	agent/core/session.py	Durum, olay kuyruğu, kesintiler
Araç Yönlendirici	agent/core/tools.py	19 aracın yönetimi
Bağlam Yöneticisi	agent/core/context_manager/manager.py	Sohbet geçmişi, 170k token'da otomatik sıkıştırma
Doom Loop Dedektörü	agent/core/doom_loop.py	Tekrarlayan başarısız desenleri algılar
Backend	backend/main.py	FastAPI uygulaması
Frontend	frontend/src/App.tsx	React chat arayüzü
19 Araç (Tools)
Araç	Amaç
papers_tool	HF Papers arama, okuma, atıf grafikleri
dataset_tools	Dataset şema doğrulama
docs_tools	HF dokümantasyon arama/okuma
github_find_examples	Çalışan örnek script bulma
github_read_file	GitHub dosya okuma
hf_repo_files_tool	HF repo dosya yönetimi
hf_repo_git_tool	HF repo git işlemleri
jobs_tool	Cloud GPU eğitimi (T4, A10G, A100, L4, L40S)
sandbox_tool	HF Space sandbox oluşturma
sandbox_client	Sandbox üzerinde bash/read/write/edit
web_search_tool	DuckDuckGo arama
research_tool	Alt-ajan araştırma
plan_tool	Yapılacaklar listesi
notify_tool	Bildirim gönderme
4. Kimler İçin?
ML Mühendisleri/Araştırmacılar — Tekrarlayan eğitim pipeline'larını otomatikleştirme
Veri Bilimciler — Yeni datasetlerde hızlı prototipleme
HF Güç Kullanıcıları — Hub, Jobs, Spaces derin entegrasyonu
AI Ajan Geliştiricileri — Referans implementasyon
Öğrenciler — Ajanın araştırma odaklı yaklaşımını gözlemleyerek öğrenme
5. Nasıl Kullanılır?
CLI (GitHub)
# Kurulum
git clone git@github.com:huggingface/ml-intern.git
cd ml-intern
uv sync
uv tool install -e .

# .env dosyası oluştur
ANTHROPIC_API_KEY=<anahtar>
HF_TOKEN=<token>

# Etkileşimli mod
ml-intern

# Kafasız mod (tek komut)
ml-intern "fine-tune llama on my dataset"

# Belirli model ile
ml-intern --model anthropic/claude-opus-4-6 "your prompt"
Web (HF Space)
https://huggingface.co/spaces/smolagents/ml-intern adresine git
HF hesabınla giriş yap
Model seç (ücretsiz/pro)
Sohbet arayüzünde komut yaz
Hassas işlemler için onay ver
Özel Komutlar
/model                    # Model değiştir
/share-traces public      # İzlemeleri herkese aç
/share-traces private     # İzlemeleri gizle
/compact                  # Bağlamı manuel sıkıştır
/undo                     # Son işlemi geri al
/help                     # Yardım
6. Güvenlik Özellikleri
Onay sistemi: Yıkıcı işlemler (jobs, sandbox) için açık onay
Bütçeli otomatik onay: YOLO modu ile maliyet limiti
Doom loop algılama: Tekrarlayan başarısız desenleri kırma
Bağlam sıkıştırma: 170k token'da otomatik sıkıştırma
Bozuk JSON kurtarma: Geçersiz argümanları algılama ve düzeltme
7. smolagents ile İlişkisi
ML Intern, smolagents ekibi tarafından geliştirilmiştir. smolagents minimal ajan kütüphanesiyken; ML Intern bunun üzerine inşa edilmiş tam özellikli uygulamadır:

Derin HF ekosistem entegrasyonu
Web UI + CLI çift arayüz
19 özel araç
Cloud compute desteği
8. Ekstra Sorular ve Cevaplar
Q: Her işlem için onay mı vermem gerekiyor?
A: Hayır. configs/cli_agent_config.json içinde auto_approve ayarları var. Yıkıcı olmayan işlemler (araştırma, kod okuma) otomatik; yıkıcı işlemler (eğitim job'u başlatma, dosya silme) için onay istenir.

Q: Eğitim modelleri nereye kaydediliyor?
A: push_to_hub=True ile HF Hub'a. Eğer unutursan, job ephemeral storage'ı silindiğinde model kaybolur!

Q: Ücretsiz kullanabilir miyim?
A: Web arayüzünde Kimi, MiniMax, GLM, DeepSeek ücretsiz. Claude/GPT için kredi gerekir. CLI'da kendi API anahtarını kullanırsan maliyeti kendin ödersin.

Q: Yerel modeller çalıştırabilir miyim?
A: Evet! CLI'da ollama/llama3.1:8b veya vllm üzerinden yerel modeller kullanılabilir.

Q: Session'lar kaydediliyor mu?
A: Evet. Her session {hf-username}/ml-intern-sessions dataset'ine JSONL formatında kaydedilir. HF Agent Trace Viewer ile görüntülenebilir.

Q: Birden fazla session aynı anda?
A: Web arayüzünde evet, sol panelden yeni session oluşturulabilir. CLI'da her çalıştırma yeni session'dır.

Q: MCP sunucuları destekleniyor mu?
A: Evet! configs/mcp_servers_config.json ile özel MCP sunucuları eklenebilir.

Bu proje, literatürden beslenen, kendi kendine araştırma yapabilen, kod yazabilen ve cloud GPU'da eğitim başlatabilen tam otonom bir ML asistanı olarak konumlandırılıyor.