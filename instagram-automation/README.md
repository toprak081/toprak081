# Instagram Otomasyonu (n8n)

Her gün 10:00'da: Claude ile caption üret → Instagram'a görsel olarak paylaş.

## Kurulum
1. n8n'de **Import from File** ile `workflow.json` dosyasını içe aktar.
2. Credentials oluştur:
   - **Anthropic**: Header Auth, ad `x-api-key`, değer API anahtarın.
   - **Instagram Graph**: Query Auth, ad `access_token`, değer uzun ömürlü token.
3. "Ayarlar" düğümünde `topic`, `imageUrl` (herkese açık URL) ve `igUserId` değerlerini doldur.
4. Workflow'u **Active** yap.

## Gereksinimler
- Instagram **Business/Creator** hesabı + bağlı Facebook Sayfası
- Meta Developer uygulaması; `instagram_content_publish` izni
- Görsel URL'si JPEG ve herkese açık olmalı

## Geliştirme fikirleri
- Konu/görsel listesini Google Sheets'ten satır satır çekmek
- Reels için `media_type=REELS` + `video_url`
