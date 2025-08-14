# 💧 Su Seviyesi Gösterge Devresi (İletkenlik Tabanlı)

Bu proje, su tanklarının seviyesini **LED göstergelerle uzaktan** izlemeye yarayan basit bir seviye ölçüm devresidir. 
Demo için 0.5 L pet şişe sensör gövdesi olarak kullanılmış, gerçek kullanım için 2–3 tonluk tanklara ölçeklenebilir.

## 🧰 Malzemeler
- 1× 0.5 L pet şişe (demo gövdesi)
- 1× kalın bakır tel (1–2 mm) – **ana elektrot (anot)**
- 4× seviye prob kablosu (sensör elektrotları)
- 4× NPN transistör (ör. BC547/2N3904 vb.)
- 4× LED
- 1× On/Off anahtar (switch)
- 1× 9 V pil + pil başlığı
- Tahta plaka (montaj için), küçük vida/kelepçe
- Silikon (sızdırmazlık ve mekanik sabitleme için)
- Lehim, kablo

> **Not:** LED ve baz dirençleri, akım sınırlama ve transistör koruması için önerilir.

## 🧱 Mekanik Kurulum
- Devre elemanları **tahta plaka** üzerine lehimlenip sabitlendi.
- Pet şişe, plakanın kenarına **silikon** ile yapıştırıldı (sızdırmaz ve sağlam).
- Pet şişenin belirli seviyelerine küçük delikler açıldı; bu deliklere **prob kabloları** yerleştirildi ve sızdırmazlık için silikonla kapatıldı.
- Şişenin en altına **kalın bakır tel** (ana elektrot) yerleştirildi.

## ⚙️ Çalışma Prensibi
Sıvı (su) belirli bir seviyeye ulaştığında, en alttaki ana elektrot (bakır tel, +9V) ile o seviyedeki prob kablosu arasında **iletken bir yol** oluşur. 
Bu küçük akım, probdan transistörün **baz**ına (baz direnci üzerinden) uygulanır. Baz tetiklenince transistör **iletime** geçer; 
LED devresi (LED + seri direnci) kolektör–emiter üzerinden tamamlanır ve **ilgili LED yanar**. Su seviyesi yükseldikçe üst seviyelerin LED’leri sırasıyla yanar.

Basitleştirilmiş bağlantı mantığı:
- **Ana elektrot (bakır tel)** → 9V **+** kutup
- **Her LED’in anot ucu** → ana elektroda (direnç üzerinden)
- **LED’in katodu** → ilgili transistörün **kolektörü**
- **Transistör emiteri** → **anahtar** → 9V **–** (GND)
- **Seviye probu** → **baz direnci** → transistör **bazı**

> **Neden LED seri direnci?** LED’lerin aşırı akım çekmesini önler ve ömrünü uzatır.  
> **Neden baz direnci?** Su iletkenliği değişkendir; baz akımını sınırlamak transistörü korur ve yalancı tetiklemeleri azaltır.

## 🔌 Besleme
- 9 V pil ile çalışır. Uzun süreli kullanımda 5 V adaptör + regülatör ile besleme önerilir.

## 📐 Kalibrasyon / İyileştirme İpuçları
- **Baz direnci** (10k–100kΩ): Su iletkenliği düşükse (özellikle temiz içme suyu), daha **düşük** değer seçmek tetiklemeyi kolaylaştırır. İletkenliği yüksek (tuzlu) suda daha **yüksek** değer yalancı tetiklemeyi azaltır.
- **LED seri direnci**: LED rengine göre 220–1kΩ aralığında deneyerek parlaklık/akımı ayarlayın.
- **Korozyon**: Bakır ve sıradan kablolar suda zamanla korozyona uğrar. Uzun ömür için **paslanmaz çelik elektrot** kullanın, düşük voltaj (5 V civarı) tercih edin, elektrotlara **AC uyarım** (ileri seviye) korozyonu azaltır.
- **Gürültü/Yalancı Tetikleme**: Baz–GND arasına **yüksek değerli pull-down** (ör. 1MΩ) eklemek ve kabloları **gölgelemek** (shield) kararlılığı artırır.


