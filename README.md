# 🧠 COVID-19 Makalelerinde NLP Tabanlı Metin Analizi ve Akıllı Arama Sistemi

Bu projede, COVID-19 hakkında yayımlanmış akademik makaleleri içeren **CORD-19 veri seti** üzerinde **Doğal Dil İşleme (NLP)** teknikleri kullanarak metin analizi yaptım. Temel amacım; makale özetlerinden anlamlı bilgiler çıkarmak, sık geçen terimleri görselleştirmek ve kullanıcı tarafından yapılan sorgulara göre en alakalı makaleleri sıralamak.

---

## Veri Seti

- **Kaynak:** [CORD-19 Open Research Dataset](https://www.kaggle.com/datasets/allen-institute-for-ai/CORD-19-research-challenge)
- **Kullanılan dosya:** `metadata.csv`
---

## Kullanılan Teknolojiler

- Python 3
- Pandas, NumPy
- NLTK (lemmatization, stopwords)
- Scikit-learn (TF-IDF, cosine similarity)
- WordCloud
- Matplotlib

---

## Proje Aşamaları

### 1. Veri Ön İşleme
Her makale özetini şu işlemlerden geçirdim:
- Küçük harfe çevirme
- Noktalama işaretleri ve sayıları kaldırma
- Stopword (gereksiz kelime) temizliği
- Lemmatization (kelimeleri kök haline getirme)

### 2. TF-IDF Vektörleştirme
- Temizlenen özetler `TfidfVectorizer` ile sayısal forma dönüştürdüm.
- Parametreler: `max_df=0.8`, `min_df=2`

### 3. Kelime Frekans Analizi
- TF-IDF matrisinden en yüksek skorlu kelimeler çıkardım.
- Literatürde en çok geçen anlamlı kelimeler listeledim.

### 4. Görselleştirme
- **WordCloud:** En sık geçen kelimelerin görsel bulutu oluşturdum.

### 5. Akıllı Arama Sistemi
Kullanıcıların ilgilendiği konulara göre en alakalı makaleleri sıralayan basit bir arama sistemi geliştirdim:
- Sorgu cümlesi ön işlenir ve TF-IDF ile vektörleştirilir.
- Cosine similarity ile özetlerle benzerlik hesaplanır.
- En alakalı makaleler başlık, özet, dergi ve yayın tarihi bilgisiyle sıralanır.
