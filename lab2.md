# LABORATUVAR 2 - IEC 62443 Mini Workshop
Makine: Kaplan Makina Helezon Konveyör (Vidalı Taşıma Bandı)
Çıktı: Zone / Conduit Diagram

Ad Soyad: İkra Aslan
Grup: Gece-B
Tarih: 23.10.2026

Görev A - varlıkları bölgelere ayırın

Varlık listesi:
PLC · HMI · Helezon motor sürücüsü (VFD) · Safety PLC · SCADA istemcisi · Mühendislik istasyonu · Uzak servis erişimi · Ofis ağı (ERP/e-posta)

1. Hangi varlıklar aynı bölgede? Bölgeleri adlandırıp gruplandırın.
Ofis Bölgesi: Ofis ağı (ERP/e-posta). Uzak Erişim / DMZ Bölgesi: Uzak servis erişimi. İzleme ve Mühendislik Bölgesi: SCADA istemcisi, Mühendislik istasyonu. Makine Kontrol Bölgesi: PLC, HMI, Helezon motor sürücüsü (VFD). Emniyet Bölgesi: Safety PLC.

2. Safety PLC'yi hangi bölgeye koydunuz - neden?
Ayrı bir Emniyet Bölgesine koyduk çünkü insan hayatını koruyan en kritik cihazdır ve normal kontrol ağındaki bir siber müdahaleden veya arızadan kesinlikle etkilenmemelidir.

3. Bölgeler arası geçişler (conduit) nerede? Her geçişte ne kontrol edilecek?
Ofis ile SCADA arasında güvenlik duvarı ile sadece üretim verisine izin verilir. Uzak erişim ile iç ağ arasında VPN, MFA ve Jump server kontrolü yapılır. Makine kontrol ile Emniyet PLC'si arasında ise sadece salt okunur durum bilgisi geçer, yazma kapatılır.

Görev B - uzak erişim kararı (6 satır)

| Karar | Seçenekler | Seçiminiz + nedeni |
| :--- | :--- | :--- |
| Aracı? | Doğrudan / Jump server | **Jump server** seçilir, dışarıdaki bilgisayarın makine ağına doğrudan erişmesini önlemek için. |
| Tünel? | Açık / VPN | **VPN** seçilir, internet üzerinden geçen bakım verisini şifreleyerek dinlemeyi engellemek için. |
| Kimlik? | Parola / MFA | **MFA** seçilir, parola çalınsa bile ikinci doğrulama olmadan sisteme girilmesini önlemek için. |
| Hesap? | Paylaşılan / Kişisel | **Kişisel** seçilir, ortak hesap yerine kimin hangi değişikliği yaptığını bilmek için. |
| Kayıt? | Yok / Tam oturum kaydı | **Tam oturum kaydı** seçilir, yapılan tüm parametre değişikliklerini geriye dönük inceleyebilmek için. |
| Zamanlama? | Sürekli açık / Varsayılan kapalı | **Varsayılan kapalı** seçilir, sadece sahadaki operatör bakım onayı verdiğinde bağlantıyı açmak için. |
