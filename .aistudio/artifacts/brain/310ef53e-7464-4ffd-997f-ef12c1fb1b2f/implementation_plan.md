# CareerPulse AI — Mülakat Simülasyonu & Akıllı Kariyer Koçu

Mülakat yapılacak kişinin unvanına (titr), şirket dinamiklerine ve rol seviyesine göre kişiselleştirilmiş potansiyel soru üretimi ve interaktif simülasyon sunan; aynı zamanda kullanıcının tamamladığı eğitimleri (metin, dosya özeti veya yapılandırılmış formla) analiz ederek sonraki kariyer adımı için eksik beceri analizi, somut kurs/sertifika önerileri ve adım adım gelişim yol haritası sağlayan uçtan uca kariyer koçluğu platformu.

---

### User Review & Critical Decisions

> [!IMPORTANT]
> Kullanıcı yanıtları doğrultusunda netleşen temel mimari ve ürün kararları:

- **Confirmed Decision 1 (İnteraktif Simülasyon & Puanlama)**: Mülakat modu sadece statik bir soru listesi çıkarmakla kalmayacak; kullanıcı isterse mülakatçının rolüne bürünmüş yapay zeka ile soru-cevap simülasyonu gerçekleştirebilecek, verdiği cevaplar için STAR (Situation, Task, Action, Result) metodu, teknik derinlik ve iletişim puanı üzerinden anlık yapıcı geri bildirim alabilecek.
- **Confirmed Decision 2 (Hibrit Eğitim Girişi)**: Eğitim geçmişi girişi kullanıcının tercihine uygun olarak birleştirilmiştir: Hem serbest metin/doküman/sertifika özeti yapıştırma/yükleme hem de kurs adı, sağlayıcı (Coursera, Udemy, Üniversite vb.), kazanılan yetkinlikler ve etiketler ile yapılandırılmış kart/form girişi bir arada desteklenecek.
- **Confirmed Decision 3 (Ayrıntılı Yol Haritası ve Eksik Beceri Analizi)**: Kariyer koçu modülü, tamamlanan eğitimleri hedef pozisyonla kıyaslayarak somut "Beceri Açığı (Skill Gap)" matrisi, önceliklendirilmiş kurs/sertifika tavsiyeleri (ör. AWS Solutions Architect, Advanced System Design, Strategic Leadership) ve 30-60-90 günlük eylem planı sunacak.
- **Model Seçimi**: Gerçek zamanlı, güvenilir ve yüksek performanslı akıl yürütme için sunucu tarafı `gemini-3.8-flash` modeli yapılandırılmış JSON ve akış yanıtları ile kullanılacak.

---

### 1. Overview & Core Concept

- **What It Does**:
  1. **Mülakat Hazırlığı & Simülasyon Modülü**: Kullanıcı mülakata gireceği kişinin unvanını (örn. *VP of Engineering*, *Senior Product Manager*, *HR Director*, *Lead Data Scientist*), şirket türünü ve rol seviyesini girer. Sistem, bu profildeki bir mülakatçının zihninden en kritik 8-12 potansiyel soruyu (davranışsal, teknik/fonksiyonel, case ve ters köşe sorular) soru amaçları ve ideal cevap tüyolarıyla üretir. Kullanıcı dilerse "Canlı Simülasyon" başlatarak soruları sırayla cevaplar, yapay zekadan puanlama ve düzeltme önerileri alır.
  2. **Eğitim Analizi & Sonraki Adım Kariyer Yol Haritası**: Kullanıcı bugüne kadar aldığı eğitimleri, bootcamp'leri, sertifikaları veya şirket içi eğitim içeriklerini girer. Sistem bu birikimi analiz eder, güçlü olduğu alanları haritalandırır ve kullanıcının hedeflediği kariyer sıçraması için eksik kalan kritik yetkinlikleri ve somut eğitim programlarını (hangi platform, hangi konu başlıkları, ne kadar süre) çıkarır.
  3. **Hazır Örnekler & Profil Yönetimi**: Kullanıcının hızlıca deneyebileceği popüler mülakatçı profilleri (Tech Lead, HR Partner, Startup Founder vb.) ve örnek eğitim geçmişleri hazır şablonlar olarak sunulur.

- **Target Audience / Persona**:
  - Yeni bir pozisyona veya terfi mülakatına hazırlanan profesyoneller.
  - Mülakatı yapacak kişinin unvanına ve bakış açısına göre stratejik hazırlanmak isteyen adaylar.
  - Aldığı dağınık eğitimleri anlamlı bir kariyer sıçramasına dönüştürmek için somut yol haritasına ihtiyaç duyan yaşam boyu öğrenenler.

- **Key Value**:
  - Karşıdaki kişinin unvanına özgü empati ve soru tahminleme kabiliyeti (ör. bir VP of Engineering maliyet/ölçek sorarken, bir Lead Developer kod temizliği ve test coverage sorar).
  - Aldığı eğitimlerin eksik bıraktığı kör noktaları tespit edip zaman ve para kaybını önleyen stratejik kurs önerileri.

---

### 2. User Experience & Visual Design

- **Key User Flows**:
  1. **Üst Sekmeler / Mod Geçişi**:
     - `Mülakatçı Analizi & Simülasyon` (Interviewer Persona & Mock Interview)
     - `Eğitim Geçmişi & Beceri Matrisi` (My Education Portfolio)
     - `Kariyer Koçu & Yol Haritası` (Skill Gap & Next Step Recommendations)
  2. **Akış 1: Mülakatçı Odaklı Soru & Simülasyon**:
     - Mülakatçının titri girilir (örn: *Head of Engineering*, *Senior Talent Acquisition Specialist*).
     - Opsiyonel ek detaylar: Şirket kültürü (Enterprise / Seri B Startup / Kurumsal), Mülakat Yapılan Rol, Deneyim yılı.
     - Tek tıkla "Mülakatçının Zihnini Çözümle" butonu.
     - Kartlar halinde kategorize edilmiş sorular (Davranışsal, Stratejik, Teknik, Beklenmedik). Her soruda "Mülakatçı neyi ölçüyor?" ve "STAR Cevap Taktikleri".
     - "İnteraktif Pratik Yap" butonuna basıldığında soru-cevap alanı açılır, aday cevabını yazar veya sesli söyler gibi girer; AI anında STAR değerlendirmesi, Güçlü Yönler ve Gelişim Puanı üretir.
  3. **Akış 2: Hibrit Eğitim Girişi & Portföy**:
     - Kullanıcı serbest metin/özet yapıştırabilir veya önceden tanımlanmış formla (Eğitim Adı, Kurum, Tarih, Kazanılan Yetkinlikler) ekleme yapabilir.
     - Hazır eğitim şablonları ("Full-Stack Bootcamp", "Agile & Scrum Master", "Data Analysis with Python") ile tek tıkla zenginleştirilebilir.
     - Analiz butonuna basıldığında kazanılan yetkinlikler görsel bir yetkinlik bulutu ve seviye göstergesiyle özetlenir.
  4. **Akış 3: Sonraki Adım Eğitim & Kariyer Tavsiyesi**:
     - Mevcut eğitimlerin kapsamadığı "Kritik Yetkinlik Açıkları".
     - Önceliklendirilmiş somut eğitim/kurs önerileri (Kurs türü, önerilen platform, kazanılacak anahtar yetkinlik, tahmini süre).
     - 3 Aşamalı Yol Haritası (Öncelik 1: Acil Temel Taşlar, Öncelik 2: İleri Seviye Uzmanlık, Öncelik 3: Stratejik Liderlik / Fark Yaratanlar).
     - PDF / Markdown olarak raporu dışa aktarma seçeneği.

- **Visual Identity & Theme**:
  - *Aesthetic Direction*: Prestijli, modern, net ve kurumsal kariyer stüdyosu estetiği (Executive Career Studio). AI-slop klişelerinden uzak; temiz tipografi, yüksek kontrast, sakin renk paleti.
  - *Color Palette*:
    - Canvas: Saf ve ferah koyu arduvaz / derin lacivert zemin (`bg-slate-950` ve `bg-slate-900`) veya berrak açık yüzey (`bg-slate-50`). Proje için odaklanmayı artıran, gözü yormayan modern Slate-Midnight teması (`#090D16` zemin, `#111827` kartlar, `#1E293B` sınırlar).
    - Vurgu (Accent): Dinamik indigo-kobalt (`#3B82F6` ve `#6366F1`) ve başarı için rafine zümrüt yeşili (`#10B981`).
    - Tipografi: Başlıklar ve navigasyon için `Plus Jakarta Sans`, gövde metinleri için yüksek okunurluklu `DM Sans`, skorlar ve metrikler için `font-mono tabular-nums`.
  - *Anti-Slop & Zero-Pill Rules*:
    - Rozet yığını veya anlamsız hap (pill) kutuları yok; kategoriler ve tarihler zarif metin ayraçlarıyla (`·`, `/`) sunulur.
    - Sahte "99% INNOVATION SCORE" yok; net ve açık değerlendirme kriterleri (STAR yapısı, Teknik derinlik, Örnekleme başarısı).
    - Butonlar doğrudan eylem odaklı: `"Soruları Üret"`, `"Simülasyona Başla"`, `"Gelişim Haritasını Çıkar"`.

---

### 3. Key Product Decisions & Trade-Offs

- **Decision 1: Full-Stack Express + Server-Side Gemini API**:
  - *Chosen Approach*: Tüm Gemini API çağrıları `@google/genai` kullanılarak sunucu tarafında (`server.ts`) Express proxy rotaları üzerinden çalıştırılır (`/api/interview/generate-questions`, `/api/interview/evaluate-answer`, `/api/career/recommend-trainings`).
  - *Why*: API anahtarının istemciye sızmasını engeller, büyük prompt şablonlarını ve yapılandırılmış JSON şemalarını güvenle yönetir, frontend performansını maksimize eder.
- **Decision 2: Yapılandırılmış JSON Çıktısı (Structured Outputs)**:
  - *Chosen Approach*: Gemini API'ye `responseMimeType: "application/json"` ve açık veri şemaları verilerek her sorunun kategorisi, ölçtüğü yetkinlik ve ipuçları; eğitim tavsiyelerinin ise zorluk, süre ve platform eşleştirmeleri kesin veri yapısıyla alınır.
  - *Why*: UI tarafında hatasız render, filtreleme, puanlama ve interaktif kart deneyimi sağlar.
- **Decision 3: İstemci Tarafı Güvenli Yerel Depolama (Persistence)**:
  - *Chosen Approach*: Kullanıcının girdiği eğitim portföyü ve tamamladığı simülasyon sonuçları `localStorage`'da otomatik saklanır.
  - *Why*: Kullanıcı sayfayı yenilediğinde eğitim geçmişini veya mülakat notlarını kaybetmez, üyelik zorunluluğu olmadan anında kullanılabilir.

---

### 4. Technical Architecture & Data Strategy

```
┌────────────────────────────────────────────────────────────────────────┐
│                        CareerPulse Studio (Client)                     │
│                                                                        │
│  ┌───────────────────────┐  ┌──────────────────────┐  ┌─────────────┐  │
│  │ Interviewer Studio    │  │ Education Portfolio  │  │ Career Map  │  │
│  │ - Title/Role Input    │  │ - Hybrid Form / Paste│  │ - Gap Matrix│  │
│  │ - Questions Grid      │  │ - Skills Tagging     │  │ - Next Steps│  │
│  │ - Interactive Mock Q&A│  │ - Template Library   │  │ - Roadmaps  │  │
│  └──────────┬────────────┘  └──────────┬───────────┘  └──────┬──────┘  │
│             │                          │                     │         │
│             ▼                          ▼                     ▼         │
│  ┌──────────────────────────────────────────────────────────────────┐  │
│  │ Client API Service & State Store (React Hooks + LocalStorage)     │  │
│  └─────────────────────────────────┬────────────────────────────────┘  │
└────────────────────────────────────┼───────────────────────────────────┘
                                     │  HTTP POST (JSON)
                                     ▼
┌────────────────────────────────────────────────────────────────────────┐
│                        Express Backend (Server-Side)                   │
│                                                                        │
│  POST /api/interview/generate-questions                                │
│  POST /api/interview/evaluate-answer                                   │
│  POST /api/career/recommend-trainings                                  │
│                                                                        │
│  ┌──────────────────────────────────────────────────────────────────┐  │
│  │ @google/genai SDK (gemini-3.8-flash, Server User-Agent telemetry)│  │
│  └─────────────────────────────────┬────────────────────────────────┘  │
└────────────────────────────────────┼───────────────────────────────────┘
                                     │  Secure API Key
                                     ▼
                      Google Gemini 3.8 Flash Engine
```

#### Veri Yapıları (Data Contracts):
1. **InterviewQuestion**:
   - `id`, `category` (Teknik, Davranışsal, Liderlik, Case, Beklenmedik), `question`, `interviewerObjective`, `recommendedApproach`, `sampleAnswerOutline`
2. **AnswerFeedback**:
   - `score` (1-100), `starEvaluation` { situation, task, action, result }, `strengths` (string[]), `improvementPoints` (string[]), `refinedResponse`
3. **CompletedTraining**:
   - `id`, `title`, `providerOrInstitution`, `dateOrDuration`, `acquiredSkills` (string[]), `summaryNotes`
4. **CareerRecommendationResult**:
   - `skillGaps`: Array<{ skill: string, importance: 'high' | 'medium' | 'critical', reason: string }>
   - `recommendedCourses`: Array<{ title: string, platform: string, priority: 'P1' | 'P2' | 'P3', duration: string, outcome: string, curriculumHighlights: string[] }>
   - `roadmapPhases`: Array<{ phase: string, timeframe: string, goal: string, actionItems: string[] }>

---

### Step-by-Step Execution Plan

1. **Sunucu Mimarisi & API Rotaları (`server.ts`)**:
   - Express sunucusu oluşturma, `@google/genai` istemcisi yapılandırması (`gemini-3.8-flash`, `httpOptions: { headers: { 'User-Agent': 'aistudio-build' } }`).
   - Mülakatçı soruları üretme endpoint'i (`/api/interview/generate-questions`).
   - Cevap değerlendirme ve koçluk endpoint'i (`/api/interview/evaluate-answer`).
   - Eğitim açığı ve gelişim tavsiyesi endpoint'i (`/api/career/recommend-trainings`).
   - Geliştirme ortamında Vite middleware / dev sunucusu köprüsü ve üretim build desteği.

2. **Frontend Arayüzü & Bileşenler**:
   - Üst Bar: Marka adı (`CareerPulse AI`), mod sekmeleri ve hızlı aksiyonlar.
   - `InterviewerAnalyzer`: Mülakatçı titri, şirket tipi, rol seçimi ve üretilen akıllı soru kartları.
   - `MockInterviewSimulator`: Seçilen soruya canlı cevap yazma, anlık AI değerlendirmesi, STAR analizi ve puan kartı.
   - `EducationManager`: Hibrit giriş (metin yapıştırma + yapılandırılmış form), yetkinlik etiketleri, hazır eğitim şablonları.
   - `CareerCoachRoadmap`: Beceri açığı matrisi, önceliklendirilmiş somut kurs tavsiyeleri ve 3 aşamalı eylem yol haritası.

3. **Veri ve Deneyim İnce Ayarı**:
   - Gerçekçi Türkçe ve uluslararası unvan desteği (örn. "Engineering Manager", "Kıdemli İK Yöneticisi", "Lead Solution Architect").
   - LocalStorage ile otomatik kaydetme ve örnek senaryoları tek tıkla yükleme (Demo Data).
   - Derleme ve tip güvenliği doğrulaması (`compile_applet`).
