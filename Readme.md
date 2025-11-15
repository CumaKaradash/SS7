Bu, SS7 (Signaling System No. 7) protokolünü, hem temel kavramları hem de modern ağ entegrasyonu ile güvenlik konularını kapsayan, tüm kaynakların atıflandığı nihai teknik dokümandır.

---

# Signaling System No. 7 (SS7) Protokolü

## Giriş
**Signaling System No. 7 (SS7)**, modern telekomünikasyon sistemlerinin bel kemiği olarak kabul edilen bir protokoller dizisidir. 1970'lerde geliştirilmiş olan SS7, telefon ağları arasında çağrı kurma, sonlandırma ve yönlendirme gibi işlevlerin yanı sıra kısa mesaj hizmetleri (SMS), dolaşım (roaming) ve numara doğrulama gibi hizmetlerin sağlanmasında kritik bir rol oynamaktadır. SS7, sinyalleşme mesajlarını ses kanallarından ayrı (band dışı) bir ağ üzerinden taşır.

## Tarihçesi ve Amacı
SS7, telekomünikasyon sistemlerinin analogdan dijitale geçiş sürecinde ortaya çıkmıştır. Protokol, eski sistemlerdeki kısıtlamaları aşarak uluslararası çağrı ve mesajlaşma gibi hizmetlerin standardize edilmesi amacıyla geliştirilmiştir. Uluslararası Telekomünikasyon Birliği (ITU) tarafından tanımlanmış ve standardize edilmiştir. **ITU-T Q.700 serisi**, SS7 protokolüne ilişkin teknik spesifikasyonları kapsamaktadır.

---

## 3. Teknik Yapısı ve Protokol Yığını

SS7, OSI (Open Systems Interconnection) modeline benzer şekilde katmanlı bir mimariye sahiptir.

| Katman | Protokol | Açıklama |
| :--- | :--- | :--- |
| **MTP Level 1** | Fiziksel Katman | Fiziksel iletim ortamını tanımlar (TDM tabanlı E1/T1 hatları gibi). |
| **MTP Level 2** | Bağlantı Katmanı | Protokol çerçeveleme, sıralama, akış kontrolü, hata algılama ve düzeltme işlevlerini gerçekleştirir. Uçtan uca hatasız iletimi sağlar. |
| **MTP Level 3** | Ağ Katmanı | Ağ yönlendirmesi ve sinyal işleme işlevlerini içerir. Mesajların **Point Code**'lara göre doğru düğümlere iletilmesini sağlar. |
| **SCCP** | **Signaling Connection Control Part** | Mesajların yönlendirilmesini ve adreslenmesini sağlar; özellikle gelişmiş telekom hizmetlerinde kritik bir rol oynar. **Global Title Translation (GTT)** yeteneğini sunar. |
| **ISUP** | **Integrated Services Digital Network User Part** | Çağrı kurma ve sonlandırma gibi işlemler için kullanılır; sesli aramalarda temel bir bileşendir. |
| **TCAP** | **Transaction Capabilities Application Part** | SS7 üzerinden bilgi alışverişi yapan uygulamalar için bir protokoldür (Örn: Numara taşıma, kredi kartı doğrulama). |
| **MAP** | **Mobile Application Part** | TCAP üzerinde çalışır ve GSM/UMTS ağlarında dolaşım, SMS iletimi ve konum yönetimi gibi mobil hizmetleri sağlar. |

---

## 4. Ağ Mimarisi ve Sinyalleşme Noktaları

SS7 sinyalleşme noktaları (Signaling Points), ağdaki işlevlerine göre sınıflandırılır:

* **Hizmet Anahtarlama Noktası (SSP - Service Switching Point):** Çağrıları başlatan, sonlandıran ve bağlayan santrallerdir. SSP'ler, bir çağrının tamamlanması için ses devrelerinin kurulması, yönetilmesi ve kaldırılması amacıyla diğer SSP'lere işaretleşme mesajlarını gönderir.
* **Sinyal Transfer Noktası (STP - Signal Transfer Point):** SS7 ağının **yönlendiricisi (router)** olarak görev yapar. Mesajları hedefine iletir ve ağ trafiğini yönetir.
* **Hizmet Kontrol Noktası (SCP - Service Control Point):** Akıllı Ağ (IN) hizmetleri, numara taşınabilirliği ve ücretsiz aramalar gibi hizmetleri yöneten merkezi veritabanı ve mantık düğümleridir.

### Sinyalleşme Bağlantı Türleri
SS7 bağlantıları işlevlerine göre sınıflandırılır:
* **A Bağı (Access Link):** Bir sinyalleşme son ucunu (**SSP** ya da **SCP**) bir **STP**'ye bağlar.
* **B Bağı (Bridge Link):** Bir **STP**'yi başka bir **STP**'ye bağlayarak sinyal akışını sağlar.

---

## 5. Adresleme ve Yönlendirme

* **Point Code (Nokta Kodu):** SS7 ağındaki her bir sinyalleşme noktasının (SSP, STP, SCP) benzersiz adresidir. Yönlendirme, MTP Level 3 tarafından bu koda göre yapılır.
* **Global Title Translation (GTT):** SCCP tarafından kullanılan ve bir telefon numarası veya IMSI gibi genel bir adresi, hedef ağ elemanının (örneğin HLR) **Point Code**'una çevirme işlemidir.

---

## 6. SS7 ve Modern Telekomünikasyon (SIGTRAN)

SS7, 5G ve VoIP gibi modern teknolojilere geçiş sürecinde yerini kısmen IP tabanlı protokollere bırakmıştır. **Diameter** ve **SIP (Session Initiation Protocol)**, SS7'nin yerini almak üzere tasarlanmış daha modern protokollerdir.

### SIGTRAN (Signaling Transport)
**SIGTRAN**, SS7 mesajlarının (özellikle MTP3 ve SCCP katmanlarından gelen verilerin) IP ağları üzerinden taşınmasını sağlayan bir teknikler dizisidir.

* **SCTP (Stream Control Transmission Protocol):** SIGTRAN'ın taşıma katmanında kullanılan, güvenilir ve bağlantı yönelimli bir protokoldür.
* **M3UA (MTP3 User Adaptation):** SS7'nin MTP Level 3'ünün üst katmanlarının (ISUP, TCAP) IP üzerinden iletimini sağlayan temel adaptasyon protokolüdür.
* **Sinyalleşme Ağ Geçidi (Signaling Gateway - SG):** Geleneksel SS7 trafiğini IP tabanlı SIGTRAN trafiğine dönüştüren ağ elemanıdır.

---

## 7. Güvenlik Zafiyetleri ve Azaltma Stratejileri

SS7, güvenliğin birincil endişe kaynağı olmadığı bir dönemde tasarlanmıştır ve çeşitli doğal güvenlik açıklarına sahiptir.

### Güvenlik Açıkları
1.  **Konum Takibi:** Saldırganlar, **MAP** protokolünü kötüye kullanarak, özellikle `anyTimeInterrogation` (ATI) gibi mesajları göndererek kullanıcıların fiziksel konumlarını izleyebilirler.
2.  **SMS Önleme ve Manipülasyon:** Banka doğrulama kodları gibi hassas bilgilerin çalınması mümkün hale gelir. Saldırganlar, sahte bir **`updateLocation`** mesajıyla SMS mesajlarını kendi cihazlarına yönlendirebilir.
3.  **Arama Dinleme:** Saldırganlar, `sendIdentification` mesajını kullanarak gelen çağrıları ele geçirebilir ve kaydedebilir.
4.  **Erişim Kontrolünün Eksikliği:** SS7 ağlarına erişimi olan bir saldırgan, çağrıları dinleyebilir ve sahte çağrılar oluşturabilir.

### Azaltma Stratejileri
* **Sinyal Güvenlik Ağ Geçitleri (SS7 Firewalls):** Kritik sinyal trafiğini denetlemek ve yetkisiz **MAP/TCAP** mesajlarını filtrelemek için kullanılır.
* **Ağ Bölgeleme (Zoning):** Çekirdek ağ elemanlarının (HLR, MSC) dış ağlardan yalıtılması ve farklı güven seviyelerine göre bölgelere ayrılması esastır.
* **Trafik Filtreleme:** Güvenilir olmayan uluslararası ağlardan gelen hassas sorguların (özellikle Konum Takibi ve SMS Yönlendirme ile ilgili olanların) engellenmesi gereklidir.
* **Düzenli Denetim:** Farklı saldırı senaryoları için tepki becerilerini değerlendirmek amacıyla düzenli sızma testleri ve tatbikatlar yapılmalıdır.

---

## 8. Kullanım Alanları
SS7'nin başlıca kullanım alanları şunlardır:

1.  **Sesli Aramalar:** Geleneksel PSTN üzerinden çağrı kurma ve yönlendirme.
2.  **SMS Hizmetleri:** Mobil ağlar arasında kısa mesajların taşınması.
3.  **Dolaşım (Roaming):** Kullanıcıların yurtdışında kendi numaralarını kullanabilmesini sağlar.
4.  **Numara Doğrulama:** Kimlik doğrulama ve çağrı yönlendirme için kullanılır.
5.  **Akıllı Ağ Hizmetleri:** Çağrı yönlendirme, çağrı bekletme ve ön ödemeli faturalama gibi gelişmiş hizmetlerin uygulanmasını sağlar.

---

## Kaynakça

1.  Signaling System No. 7 (SS7) – Orijinal Readme Dokümanı.
2.  Session Initiation Protocol (SIP) – Orijinal Readme Dokümanı.
3.  PwnLabMe. Saldırganlar SS7 Güvenlik Açıklarını Kullanarak 2FA Kodları Nasıl Çalar.
4.  Yasin Kaplan. Numara 7 İşaretleşmesi (Signalling System Number 7, SS7).
5.  sms-txt.net. SS7 Hacking Yazılımı - SMS - Çağrı - Konum.
6.  Özgür Koca. SS7'nin Düşüşü: Kritik Güvenlik Kontrolleri İşe Yarayabilir mi?.
7.  sms-txt.net. SS7 Hacking Yazılımı - Konum Takibi ve SMS Engelleme.
8.  Vikipedi. No.7 İşaretleşme Sistemi.
9.  Mpirical. Sigtran Signalling Transport.
10. ITU-T. (1993). "Q.700: Introduction to CCITT Signalling System No. 7." (Orijinal Kaynakça'dan)
11. Meyer, D., & Weiss, R. (2017). "SS7 Exploitation and Mitigation Strategies." IEEE Communications Magazine. (Orijinal Kaynakça'dan)
12. "Signaling System No. 7 (SS7) Basics." Cisco Systems, White Paper. (Orijinal Kaynakça'dan)
13. U. Fayyad, & R. Uthurusamy. (2018). "SS7 vulnerabilities: Current landscape and future directions." Journal of Network Security. (Orijinal Kaynakça'dan)
14. NIST. (2020). "SS7 and Diameter Security Guidelines." (Orijinal Kaynakça'dan)
