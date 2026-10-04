# Instagram Günlük Reklam Otomasyonu (n8n)

Her sabah 08:00:
1. Senin örnek prompt/açıklama/etiketlerinden **yeni** prompt + açıklama + etiket üretilir (Gemini, metin).
2. Yeni prompt + dükkan logosu ile reklam görseli üretilir (Gemini görsel modeli, logo referans).
3. Görsel barındırılır (imgbb) ve Instagram'da açıklama + etiketle paylaşılır.

## Kurulum
1. n8n'e `workflow.json` içe aktar.
2. Credentials (hepsi "Query Auth"):
   - Gemini: ad `key`, değer https://aistudio.google.com/apikey adresinden alınan anahtar
   - imgbb: ad `key`, değer https://api.imgbb.com anahtarı (ücretsiz)
   - Instagram: ad `access_token`, değer uzun ömürlü token
3. "Ayarlar" düğümüne ÖRNEKLERİNİ, `logoUrl` ve `igUserId` yaz.
4. Önce elle çalıştır, sonra Active yap.

## Notlar
- Abonelikler (Flow Pro, Gemini Pro, ChatGPT) API'ye bağlanmaz; Gemini API anahtarı ayrıdır (ücretsiz katman var).
- Hesap şifresi paylaşma; sadece API anahtarı kullanılır.
- Instagram Business/Creator hesabı + `instagram_content_publish` izni gerekir.
