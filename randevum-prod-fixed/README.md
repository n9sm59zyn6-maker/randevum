# Randevum V1.2 — Production MVP

Berberlerin hesap oluşturup özel randevu linki paylaşabildiği, müşterilerin üyelik olmadan randevu alabildiği mobil uyumlu web uygulaması.

## Production mimarisi
- Node.js 20
- PostgreSQL
- HTTP-only session cookie
- scrypt parola hash'i
- Rate limiting
- Randevu süresi bazlı çakışma kontrolü
- Docker
- Render Blueprint ile web + PostgreSQL birlikte kurulum
- HTTPS için Render custom domain desteği

## Kritik değişiklik
Production ortamında `DATABASE_URL` yoksa uygulama artık sessizce bellek moduna geçmez; startup başarısız olur. Böylece verilerin kalıcı olmadığı yanlış bir production kurulumu fark edilmeden kullanılmaz.

## Render
`DEPLOY-RENDER.md` dosyasındaki adımları izleyin.

Deploy sonrası:
`https://SIZIN-DOMAININIZ/health`

Beklenen:
`{"ok":true,"service":"Randevum","database":true}`

## Yasal
KVKK Aydınlatma Metni, Gizlilik ve Kullanım Şartları başlangıç şablonlarıdır. Gerçek veri sorumlusu, işletme bilgileri, saklama süreleri, sağlayıcılar ve aktarım senaryoları doldurulmadan "tam yasal" kabul edilmemelidir; son hukuki kontrol gerekir.
