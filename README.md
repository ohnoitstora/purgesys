 
# purgesys

Bu depo, `index.html` statik sayfasını kendi alan adınız `purge.rocks` altında yayınlamak (deploy) için hazırdır.

## GitHub Pages ile yayınlama

1. Bu repo `main` branch'ında `index.html` içeriyor ve kök dizinde `CNAME` dosyası ile `purge.rocks` alan adı tanımlandı.
2. GitHub'da depo ayarlarına gidin: Settings → Pages.
3. Build and deployment bölümünde Source olarak `Deploy from a branch` seçin.
4. Branch olarak `main` ve klasör olarak `/ (root)` seçin.
5. Custom domain alanına `purge.rocks` yazın ve kaydedin.
6. "Enforce HTTPS" seçeneğini etkinleştirin (sertifika hazır olduğunda aktif olur).

## DNS kayıtları

Alan adı sağlayıcınızda aşağıdaki kayıtları ekleyin:

- Apex (kökkök): `purge.rocks`
  - A kayıtları (GitHub Pages IP'leri):
    - 185.199.108.153
    - 185.199.109.153
    - 185.199.110.153
    - 185.199.111.153
  - AAAA kayıtları (IPv6):
    - 2606:50c0:8000::153
    - 2606:50c0:8001::153
    - 2606:50c0:8002::153
    - 2606:50c0:8003::153

- www alt alan adı (opsiyonel): `www.purge.rocks`
  - CNAME: `ohnoitstora.github.io`

DNS yayılımı (propagation) genelde 5–30 dakika içinde olur, bazı sağlayıcılarda 24 saate kadar sürebilir.

## 404 sayfası

Kök dizinde basit bir `404.html` eklendi. GitHub Pages, bulunamayan yollar için otomatik olarak bu dosyayı sunar.

## Yerel test

Bir tarayıcıda `index.html` dosyasını açarak yerel görüntüleme yapabilirsiniz. Gelişmiş yerel sunucu isterseniz Node.js veya Python ile basit bir HTTP sunucu çalıştırabilirsiniz.

## Sorun giderme

- Pages sayfasında hata görürseniz, `CNAME` dosyasının yalnızca `purge.rocks` içerdiğini ve branch ayarlarının `main` + root olduğunu doğrulayın.
- DNS tarafında A/AAAA kayıtları doğru IP'lere işaret etmeli; apex alanlar için CNAME kullanmayın.
- Sertifika hazır olana kadar HTTPS zorlaması gecikebilir; 1–30 dakika bekleyin.
 
