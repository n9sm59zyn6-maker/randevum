# Randevum — Render'a gerçek kurulum

Bu paket artık web servisi + PostgreSQL veritabanını tek Render Blueprint'i ile kuracak şekilde hazırlanmıştır.

## 1) GitHub
Bu klasörü GitHub'da yeni bir repository olarak yükleyin. `render.yaml` dosyası repository kökünde olmalı.

## 2) Render
Render Dashboard → New → Blueprint seçin ve GitHub repository'nizi bağlayın.

Blueprint iki kaynak oluşturur:
- `randevum` web servisi
- `randevum-db` PostgreSQL

`DATABASE_URL` otomatik olarak PostgreSQL'in connection string'ine bağlanır.

## 3) Deploy sonrası test
Açılan Render adresinin sonuna `/health` ekleyin.
Beklenen cevap:
`{"ok":true,"service":"Randevum","database":true}`

`database:false` görüyorsanız deployment tamamlanmadan önce uygulamayı kullanmayın.

## 4) Domain
Render → Web Service → Settings → Custom Domains bölümünden satın aldığınız alan adını bağlayın.
HTTPS Render tarafından sağlanır.

## 5) İlk gerçek test
1. Ana sayfada Hesap Oluştur.
2. Bir berber hesabı aç.
3. Panelde oluşan randevu linkini aç.
4. Müşteri olarak randevu oluştur.
5. Berber paneline dön ve randevunun düştüğünü kontrol et.

## Önemli
Bu proje üretim altyapısını sağlar; KVKK ve diğer hukuki metinlerde işletmeci/veri sorumlusu bilgileri doldurulmalı ve gerçek veri akışına göre hukukçu tarafından kontrol edilmelidir.
