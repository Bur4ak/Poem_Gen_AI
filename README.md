# Poem_Gen_AI

# Beyit & Şiir Creator: Türkçe Şiir Üretimi için GPT-2 Fine-Tuning

Bu proje, önceden eğitilmiş bir GPT-2 modelini kullanarak Türkçe klasik şiir (özellikle beyit ve dörtlük formlarında) üretmeyi amaçlayan bir Generatif Yapay Zeka çalışmasıdır. Model, Türk edebiyatının inceliklerini, şiirsel yapılarını ve üslup özelliklerini yakalayarak yaratıcı ve sentaktik olarak doğru şiirler üretmek üzere eğitilmiştir.

---

## 🚀 Proje Amacı

Bu projenin temel amacı, Türk şairlerinden derlenmiş özel bir veri kümesiyle önceden eğitilmiş bir GPT-2 modeline ince ayar yaparak Türkçe klasik şiirler (özellikle beyit ve dörtlük formlarında) üretmektir[cite: 1]. Model, Türk edebi eserlerinin nüanslarını, şiirsel yapılarını ve üslup özelliklerini yakalayarak yaratıcı ve dilbilgisi açısından doğru şiirler üretmek üzere eğitilmiştir[cite: 2].

---

## 🛠️ Kullanılan Metodlar ve Teknolojiler

* **Model:** GPT-2 (124M parametre) [cite: 3]
* **Teknik:** HuggingFace Trainer API ile ince ayar (Fine-tuning) [cite: 3]
* **Veri Seti:** Ünlü Türk şairlerine (örn. Yunus Emre, Fuzuli, Nazım Hikmet) ait Türkçe şiirler [cite: 3]
* **Platform:** Google Colab (GPU tabanlı eğitim) [cite: 3]
* **Kütüphaneler:** `transformers`, `datasets`, `torch`, `sklearn`, `pandas` [cite: 3]

### Model Konfigürasyonu:

| Parametre           | Değer                                        |
| :------------------ | :------------------------------------------- |
| Tokenizer           | Özel GPT-2 tokenizer (Türkçe veri üzerinde eğitilmiş) [cite: 3, 6] |
| Maksimum Dizi Uzunluğu | 128 token                                    |
| Epoch Sayısı        | 5                                            |
| Batch Boyutu        | 2                                            |
| Öğrenme Oranı       | 5e-5                                         |

---

## 🧠 Proje İş Akışı

1.  **Veri Seti Toplama ve Ön İşleme:**
    * Birden fazla Türk şairinden şiirler toplandı ve temizlendi[cite: 4].
    * Her şiir `\n\n` kullanılarak ayrıldı ve özel karakterler kaldırıldı[cite: 5].
2.  **Tokenizer Eğitimi:**
    * Benzersiz Türkçe karakterleri ve yapıları daha iyi işlemek için Türkçe şiir veri seti üzerinde yeni bir tokenizer eğitildi[cite: 6].
3.  **Model İnce Ayarı (Fine-Tuning):**
    * Temel GPT-2 modeli, HuggingFace Trainer kullanılarak Türkçe şiirler üzerinde ince ayarlandı[cite: 7].
4.  **Metin Üretimi:**
    * Kullanıcı girdisine (örn. bir kelime veya dize) göre şiirler üretildi[cite: 8].
    * Yaratıcı üretimi artırmak için **Beam Search** ve **Top-k Sampling** yöntemleri kullanıldı[cite: 9].

---

## 🚧 Karşılaşılan Zorluklar

* **GPU Sınırlamaları:** Google Colab'ın 12GB GPU'su, batch boyutunu küçük tutmayı gerekli kıldı[cite: 10].
* **Tokenizer Uyumluluğu:** Türkçe diyakritikler (şapkalı harfler) ve şiirsel hece yapıları, orijinal GPT-2 tokenizer ile uyumsuzluk gösterdi ve bu durum özel bir tokenizer gerektirdi[cite: 11].
* **Sınırlı Veri Seti Boyutu:** Sınırlı miktardaki Türkçe şiir verisi nedeniyle aşırı uyum (overfitting) riski oluştu. Erken durdurma (early stopping) gibi teknikler kullanıldı[cite: 12, 13].

---

## 📊 Model Karşılaştırması

Aşağıdaki tablo, projemizde ince ayar yapılmış GPT-2 modelinin, önceden eğitilmiş genel İngilizce GPT-2 modeli ile bazı özellikleri açısından karşılaştırmasını sunmaktadır:

| Özellik            | İnce Ayarlı GPT-2 (Bu Proje) | Önceden Eğitilmiş GPT-2 (İngilizce) |
| :----------------- | :--------------------------: | :---------------------------------: |
| Türkçe Anlama      |              ☑               |                  X                  |
| Şiirsel Yapı       |              ☑               |                  X                  |
| Yaratıcı Çıktı     |              ☑               |                  ☑                  |
| Özelleştirme Mümkün |              ☑               |                  ☑                  |

---

## 🚀 Projeyi Çalıştırma

Bu projeyi yerel olarak çalıştırmak veya ince ayarlı modeli kullanmak için aşağıdaki adımları takip edebilirsiniz:

### Ön Gereksinimler

* Python 3.x
* `pip` paket yöneticisi

### Kurulum

Gerekli kütüphaneleri yükleyin:

```bash
pip install transformers datasets torch scikit-learn pandas

 Gelecek Çalışmalar
Bu projenin potansiyel gelişim alanları şunlardır:

Daha büyük bir GPT-2 modelinin (örn. 345M veya 774M) kullanılması.
Bir kafiye (rhyme) tespit modülünün entegrasyonu.
Kullanıcıların şiir üreteci ile etkileşim kurabileceği bir web veya masaüstü GUI (grafik kullanıcı arayüzü) geliştirilmesi.
Daha iyi semantik derinlik için veri setinin genişletilmesi.
✉️ İletişim
Ad Soyad: BURAK YILDIRIM 
Öğrenci No: 220201047 
