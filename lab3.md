# LABORATUVAR 3 - Threat & Risk + Risk Matrix
Makine: Kaplan Makina Helezon Konveyör (Vidalı Taşıma Bandı)
Çıktı: Risk Register

Ad Soyad: İkra Aslan
Grup: Gece-B
Tarih: 23.10.2026

Görev - üç senaryo kurun ve puanlayın

| Senaryo (kim -> kapı -> zincir -> fiziksel sonuç) | L | S | E | Skor | Öncelik |
| :--- | :---: | :---: | :---: | :---: | :--- |
| Dış saldırgan -> sürekli açık bırakılan uzak servis bağlantısı -> PLC'ye bağlanıp temizlik sırasında helezon motoruna çalışma komutu verir -> Helezon vidası aniden döner -> Bakım yapan personelin el veya kol kaptırması sonucu uzuv kaybı. | 2 | 3 | 3 | 18 | Kritik (1. Öncelik) |
| Saldırgan -> ofis ağından ayrılmamış SCADA hattı -> sürücü hız ve tork sınırlarını maksimuma çıkarıp tıkanma korumasını kapatır -> Malzeme sıkıştığında motor durmaz ve mil kırılır -> Fırlayan mekanik parçaların operatörü yaralaması. | 2 | 2 | 2 | 8 | Orta (3. Öncelik) |
| Zararlı yazılım bulaşmış bakım bilgisayarı -> mühendislik bağlantı portu -> Safety PLC içindeki kapak kilidi parametresini devre dışı bırakır -> Üst kapak açıldığında helezon durmaz -> Operatörün dönen vidaya temas ederek ağır yaralanması. | 1 | 3 | 2 | 6 | Orta / S=3 ile 2. Öncelik |

Derecelendirme: Kritik 18-27 | Yüksek 9-17 | Orta 4-8 | Düşük 1-3

1. En yüksek öncelikli senaryonuz hangisi? Bir cümleyle: neden bu?
Birinci senaryodur çünkü açık bırakılan uzak servis kapısından kolayca girilerek bakım anında helezon başında çalışan insana doğrudan ölümcül zarar verilebilir.

2. S=3 olup skoru düşük kalan senaryonuz var mı? Nasıl görünür kılacaksınız?
Üçüncü senaryonun skoru 6 olduğu için Orta görünmektedir ancak şiddeti S=3 olduğundan insana ağır zarar riski taşır, bu yüzden risk tablosunda S=3 uyarısıyla ikinci sıraya çekerek önceliklendiririz.
