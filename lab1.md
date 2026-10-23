# LABORATUVAR 1 - Safety Architecture
Makine: Kaplan Makina Helezon Konveyör (Vidalı Taşıma Bandı)
Çıktı: Safety Function Map

Ad Soyad: İkra Aslan
Grup: Gece-B
Tarih: 23.10.2026

NORMAL KONTROL YOLU (üretim):
Sensör -> PLC (normal kumanda) -> Helezon vidası + motor
Uzak bakım modülü (internete AÇIK) -> dijital kesişim noktası

SAFETY YOLU (koruma - AYRI):
E-stop / İpli şalter + kapak kilidi -> Safety PLC (emniyet kumandası) -> STO / Kontaktör -> Safe State

Görev - sırayla cevaplayın

1. Bu makinede tehlike nedir? İnsan neyden zarar görür?
Tekne içinde dönen helezon vidası ve tahrik milidir. Besleme ağzından veya açık bakım kapağından el ya da kol kaptırma sonucu sıkışma, sürüklenme ve uzuv kaybı yaşanabilir.

2. Safety function (emniyet fonksiyonu) hangisidir?
Acil durdurma butonuna basıldığında, ipli şalter çekildiğinde veya bakım kapağı açıldığında Safety PLC üzerinden sürücü STO girişini ve kontaktörü keserek helezon vidasını durduran fonksiyondur.

3. Safety-related control system nerede? Şemada işaretleyin.
Şemadaki alt kolda yer alan E-stop / İpli şalter + kapak kilidi, Safety PLC ve STO / Kontaktör bileşenlerinden oluşan ayrı emniyet zinciridir.

4. Normal PLC ile Safety PLC farkı nedir?
Normal PLC malzeme akışını ve motor hızını yönetir, arıza durumunda çıkışı tehlikeli kalabilir. Safety PLC ise yedekli çalışır, kendi hatalarını denetler ve arızada sistemi güvenli duruşa geçirir.

5. PLr / SIL neden var? Bu fonksiyon için neden önemli?
Helezon vidasına uzuv kaptırma geri dönüşü olmayan ağır yaralanmaya yol açtığı için emniyet sisteminin bu yüksek riske uygun güvenilirlik seviyesinde tasarlanmasını sağlar.

6. Safe state (güvenli durum) nedir?
Helezon motor enerjisinin ve torkunun tamamen kesildiği, vidanın tam olarak durduğu ve kendi kendine yeniden çalışmasının engellendiği durumdur.

7. Safety function hangi dijital bağımlılıklara sahip?
Safety PLC içindeki emniyet programı, kapak kilidi ve reset parametreleri, sürücü STO ayarları, cihaz yazılımları ve mühendislik bağlantı arayüzüne bağımlıdır.

8. Siber müdahale hangi noktadan bu fonksiyonu bozar?
Uzak bakım ve mühendislik erişiminin oluşturduğu dijital kesişim noktasından içeri girilerek Safety PLC parametrelerinin değiştirilmesi veya kapak kilidinin yazılımsal olarak devre dışı bırakılmasıyla bozar.
