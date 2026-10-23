# LABORATUVAR 4 - Secure Remote Access
Makine: Kaplan Makina Helezon Konveyör (Vidalı Taşıma Bandı)
Çıktı: Secure Architecture

Ad Soyad: İkra Aslan
Grup: Gece-B
Tarih: 23.10.2026

Görev A - mevcut -> hedef

| MEVCUT (çizin/yazın) | HEDEF (beş ilkeyle yeniden tasarlayın) |
| :--- | :--- |
| Modem üzerinden doğrudan PLC ve HMI ağına bağlantı yapılıyor. | Doğrudan erişim kapatılır, şifreli VPN tüneli ve Jump server üzerinden geçilir. |
| Tüm servis ekibi tek bir ortak kullanıcı hesabı ve sabit parola kullanıyor. | Ortak hesap silinir, her bakımcıya kişisel hesap ve MFA doğrulaması tanımlanır. |
| Uzak erişim sürekli açık duruyor, sahadaki operatörün haberi olmuyor. | Bağlantı varsayılan kapalı tutulur, sadece sahadaki operatör onay verdiğinde açılır. |
| Oturum kaydı tutulmadığı için kimin hangi parametreyi değiştirdiği görülemiyor. | Yapılan tüm uzak bağlantılar ve PLC parametre değişiklikleri kayıt altına alınır. |
| Uzak erişim hattından hem Normal PLC'ye hem Safety PLC'ye yazılabiliyor. | Safety PLC'ye uzaktan yazma yolu kapatılır, sadece durum bilgisi okunmasına izin verilir. |

Görev B - functional safety köprüsü

1. Saldırgan tüm önlemlere rağmen içeri girerse: emniyet fonksiyonu etkilenir mi? Neden?
Uzak erişim hattı aynı ağ üzerinden Safety PLC'ye yazma yetkisine sahipse etkilenir çünkü saldırgan içeri girdiğinde emniyet parametrelerini değiştirebilir. Ancak Safety PLC fiziksel yazma kilidiyle veya ayrı donanımla ayrılmışsa saldırgan Normal PLC'yi ele geçirse bile kapak açıldığında STO devreye girer ve insan korunur.

2. Emniyet fonksiyonunun kontrol sisteminden bağımsız çalışması için GEREKSİNİMİ yazın (çözümü değil).
Helezon konveyörün acil durdurma ve kapak kilidi emniyet fonksiyonu, normal kontrol sisteminden ve uzak bakım bağlantısından bağımsız çalışmalı, uzaktan erişim yoluyla emniyet mantığı veya parametreleri değiştirilememeli ve siber saldırı durumunda bile güvenli duruşa geçme yeteneği korunmalıdır.
