# 🤖 RAG-Based — PDF Tabanlı Sohbet Sistemi

Dokümanlarınızla konuşun. PDF yükleyin, soru sorun — sistem ilgili bölümleri bulup cevaplar üretsin.

---

## 🧠 Nasıl Çalışır?

```
PDF Dosyası
    ↓
Metne dönüştürülür (PyPDF)
    ↓
Küçük parçalara bölünür (RecursiveCharacterTextSplitter)
    ↓
Her parça vektöre çevrilir (Google Gemini Embedding)
    ↓
Vektör veritabanına kaydedilir (Chroma)
    ↓
Soru gelince → en alakalı parçalar bulunur → LLM cevap üretir (Groq / Llama)
```

---

## 🛠️ Kullanılan Teknolojiler

| Katman | Teknoloji |
|--------|-----------|
| Embedding | Google Gemini (`gemini-embedding-001`) |
| LLM | Groq (`llama-3.1-8b-instant`) |
| Vektör DB | ChromaDB |
| Zincir | LangChain `ConversationalRetrievalChain` |
| Arayüz | Panel |
| Ortam | Google Colab |

---

## 🚀 Kurulum

### 1. Repoyu klonla
```bash
git clone https://github.com/yasir237/pdf_rag_api_gorq_google.git
cd pdf_rag_api_gorq_google
```

### 2. Google Colab'da aç
Notebook'u Colab'a yükle veya doğrudan GitHub'dan aç.

### 3. API Key'leri ekle
Colab'da sol paneldeki 🔑 (Secrets) bölümüne ekle:
- `GOOGLE_API_KEY` → [Google AI Studio](https://aistudio.google.com)
- `GROQ_API_KEY` → [Groq Console](https://console.groq.com/keys)

### 4. PDF dosyanı yükle
Colab'ın dosya panelinden PDF'ini yükle, `load_db("dosya.pdf")` satırındaki ismi güncelle.

### 5. Çalıştır
Tüm hücreleri sırayla çalıştır, arayüz açılır.

---

## ✨ Özellikler

- 📄 PDF yükleme ve otomatik işleme
- 🔍 Her cevabın hangi sayfadan geldiğini gösterme
- ⚙️ Çalışma sırasında PDF değiştirme
- 🌙 Koyu tema arayüz

---

## 📁 Proje Yapısı

```
pdf_rag_api_gorq_google/
├── pdf_rag_api_gorq_google.ipynb     # Ana notebook
├── requirements.txt     # Gerekli kütüphaneler
├── .gitignore           # Git'e gitmeyecek dosyalar
└── README.md            # Bu dosya
```

---

## ⚠️ Notlar

- PDF dosyaları `.gitignore` ile repo dışında tutulur, kendi dosyanı kendin yüklemelisin
- API key'ler Colab Secrets ile yönetilir, kod içinde görünmez
- Ücretsiz Groq ve Google API kotaları ile çalışır

---

## 👤 Geliştirici

**[Yasir Alrawi]**  
[LinkedIn](https://www.linkedin.com/in/yasir-alrawi-12814521a/) · [GitHub](https://github.com/yasir237)
