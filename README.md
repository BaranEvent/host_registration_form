# Form Builder Dashboard

Bu Streamlit uygulaması, kullanıcıların kolayca kayıt formları oluşturmasını sağlar ve Airtable'a kaydeder.

## Özellikler

- ✅ Dinamik soru ekleme
- ✅ 8 farklı veri tipi desteği
- ✅ Çoktan seçmeli sorular için dinamik seçenek ekleme
- ✅ Sürükle-bırak ile soru sıralama
- ✅ Gerçek zamanlı form önizleme
- ✅ Zorunlu alan işaretleme
- ✅ Airtable entegrasyonu

## Veri Tipleri

- **Yazı**: Metin girişi
- **Sayı**: Tam sayı girişi
- **Virgüllü sayı**: Ondalıklı sayı girişi
- **Tarih**: Tarih seçimi
- **Saat ve tarih**: Tarih ve saat seçimi
- **Doğru yanlış**: Evet/Hayır seçimi
- **Çoktan seçmeli**: Tek seçim
- **Çoktan seçmeli çoklu cevap**: Çoklu seçim

## Kurulum

1. Gerekli paketleri yükleyin:
```bash
pip install -r requirements.txt
```

2. Airtable yapılandırmasını kontrol edin:
   - `base_id`: Airtable base ID'niz
   - `api_key`: Airtable API anahtarınız

3. Uygulamayı çalıştırın:
```bash
streamlit run main.py
```

## Kullanım

1. Sol paneldeki "➕ Yeni Soru Ekle" butonuna tıklayın
2. Soru metnini girin
3. Veri tipini seçin
4. Zorunlu alan olup olmadığını belirleyin
5. Çoktan seçmeli sorular için seçenekler ekleyin
6. Sağ panelde form önizlemesini görün
7. Soruları yukarı/aşağı butonları ile sıralayın
8. "✅ Formu Uygula" butonuna tıklayarak formu Airtable'a kaydedin

## Airtable Yapısı

Form verileri Airtable'da `registration_forms` tablosuna kaydedilir:

- `event_id`: Benzersiz form kimliği
- `name`: Soru metni
- `type`: Veri tipi
- `is_required`: Zorunlu alan durumu
- `rank`: Soru sırası
- `possible_answers`: Çoktan seçmeli seçenekler (JSON formatında)

## Airtable Kurulumu

Airtable'da aşağıdaki sütunları içeren bir tablo oluşturun:

| Sütun Adı | Veri Tipi | Açıklama |
|-----------|-----------|----------|
| event_id | Single line text | Benzersiz form kimliği |
| name | Single line text | Soru metni |
| type | Single line text | Veri tipi |
| is_required | Checkbox | Zorunlu alan durumu |
| rank | Number | Soru sırası |
| possible_answers | Long text | Çoktan seçmeli seçenekler (JSON) | 