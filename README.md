# magicgamesstudio.com

Build adımı olmayan statik site. Her sayfa kendi klasöründe `index.html`, bu yüzden URL'ler temiz:

| Sayfa | URL |
|---|---|
| Ana sayfa | https://magicgamesstudio.com/ |
| Privacy Policy | https://magicgamesstudio.com/privacy-policy/ |
| Terms & Conditions | https://magicgamesstudio.com/terms-conditions/ |
| Cookies Policy | https://magicgamesstudio.com/cookies-policy/ |
| Support & veri silme | https://magicgamesstudio.com/support/ |
| app-ads.txt | https://magicgamesstudio.com/app-ads.txt |

## Yayına almadan önce doldurulacaklar

1. `index.html`: App Store, Google Play ve LinkedIn linkleri (`TODO` yorumları).
2. Geliştirici adı/adresi (Senih Yıldırım, Ataşehir / İstanbul) Privacy ve Terms'te yazılı; Play Console / App Store Connect'teki bilgilerle aynı tut.
3. `app-ads.txt`: AdMob publisher ID'yi yaz, satırın başındaki `#` işaretini kaldır.
4. E-posta: tüm sayfalar `info@magicgamesstudio.com` kullanıyor (Google Workspace).

## Yerelde önizleme

```
python -m http.server 8787
```

Sonra http://localhost:8787 adresini aç.

## Yayınlama (GitHub Pages)

1. Bu klasörü yeni bir GitHub reposuna push'la.
2. Repo > Settings > Pages > Source: `main` branch, `/ (root)`.
3. `CNAME` dosyası zaten `magicgamesstudio.com` içeriyor.
4. Domain Google Workspace üzerinden alındığı için DNS, Squarespace Domains'te yönetilir (domains.squarespace.com, Workspace hesabıyla giriş > magicgamesstudio.com > DNS > Custom records). Şunları ekle:
   - `@` için 4 adet A kaydı: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - `www` için CNAME: `<github-kullanıcı-adın>.github.io`
   - Gmail'in çalışmaya devam etmesi için mevcut **MX, TXT (SPF/DKIM) ve google-site-verification kayıtlarına dokunma**.
5. DNS oturunca Pages ayarlarından "Enforce HTTPS" kutusunu işaretle.
