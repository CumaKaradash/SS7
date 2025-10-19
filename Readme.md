## Giriş
Signaling System No. 7 (SS7), modern telekomünikasyon sistemlerinin bel kemiği olarak kabul edilen bir protokoller dizisidir. 1970'lerde geliştirilmiş olan SS7, telefon ağları arasında çağrı kurma, sonlandırma, ve yönlendirme gibi işlevlerin yanı sıra kısa mesaj hizmetleri (SMS), dolaşım (roaming) ve numara doğrulama gibi hizmetlerin sağlanmasında kritik bir rol oynamaktadır.

Bu makalede, SS7'nin teknik altyapısı, çalışma prensipleri, kullanım alanları ve güvenlik zafiyetleri ele alınacaktır. Ayrıca, SS7'nin modern telekomünikasyon sistemlerindeki yerini anlamak için tarihsel ve teknik bir perspektif sunulacaktır.

---

## SS7'nin Tarihçesi ve Amacı
SS7, telekomünikasyon sistemlerinin analogdan dijitale geçiş sürecinde ortaya çıkmıştır. Protokol, eski sistemlerdeki kısıtlamaları aşarak uluslararası çağrı ve mesajlaşma gibi hizmetlerin standardize edilmesi amacıyla geliştirilmiştir. 

SS7, Uluslararası Telekomünikasyon Birliği (ITU) tarafından tanımlanmış ve standardize edilmiştir. **ITU-T Q.700 serisi**, SS7 protokolüne ilişkin teknik spesifikasyonları kapsamaktadır.

---

## Teknik Yapısı ve Katmanları
SS7, OSI (Open Systems Interconnection) modeline benzer şekilde katmanlı bir mimariye sahiptir. Ancak, SS7 protokol yığını OSI modelinden bazı yönlerden farklılaşır. SS7'nin başlıca katmanları şunlardır:

### 1. Fiziksel Katman (MTP Level 1)
Fiziksel iletim ortamını tanımlar. Bu, TDM (Time Division Multiplexing) tabanlı E1/T1 hatları gibi ortamları içerir.

### 2. Bağlantı Katmanı (MTP Level 2)
Bu katman, hata algılama ve düzeltme gibi işlevleri gerçekleştirir. MTP Level 2, veri iletiminin güvenilirliğini sağlamak için protokol çerçeveleme, sıralama ve akış kontrolü gibi mekanizmaları kullanır.

### 3. Ağ Katmanı (MTP Level 3)
Ağ yönlendirmesi ve sinyal işleme işlevlerini içerir. SS7'nin omurgasını oluşturan bu katman, mesajların doğru düğümlere iletilmesini sağlar.

### 4. Uygulama Katmanı (Signaling Connection Control Part - SCCP)
SCCP, mesajların yönlendirilmesini ve adreslenmesini sağlar. Özellikle gelişmiş telekom hizmetlerinde kritik bir rol oynar.

### 5. Transaction Capabilities Application Part (TCAP)
TCAP, SS7 üzerinden bilgi alışverişi yapan uygulamalar için bir protokoldür. Örneğin, numara taşıma veya kredi kartı doğrulama gibi işlemleri destekler.

### 6. Integrated Services Digital Network User Part (ISUP)
ISUP, çağrı kurma ve sonlandırma gibi işlemler için kullanılır. Özellikle sesli aramalarda temel bir bileşendir.

---

## Kullanım Alanları
SS7, geniş bir kullanım alanına sahiptir. Bunlardan bazıları şunlardır:

1. ** Sesli Aramalar**: Geleneksel PSTN (Public Switched Telephone Network) üzerinden çağrı kurma ve yönlendirme.
2. ** SMS Hizmetleri**: Mobil ağlar arasında kısa mesajların taşınması.
3. ** Dolaşım (Roaming)**: Kullanıcıların yurtdışında kendi numaralarını kullanabilmesini sağlar.
4. ** Numara Doğrulama**: Kimlik doğrulama ve çağrı yönlendirme için kullanılır.

---

## Güvenlik Zafiyetleri
SS7'nin tasarlandığı dönemde, güvenlik endişeleri bugünkü kadar kritik görülmüyordu. Bunun sonucu olarak, protokolde bir dizi güvenlik açığı mevcuttur:

1. ** Erişim Kontrolünün Eksikliği**: SS7 ağlarına erişimi olan bir saldırgan, çağrıları dinleyebilir, SMS mesajlarını okuyabilir ve sahte çağrılar oluşturabilir.
2. ** Konum Takibi**: SS7'yi kötüye kullanan bir saldırgan, kullanıcıların fiziksel konumlarını izleyebilir.
3. ** SMS Önleme ve Manipülasyon**: Banka doğrulama kodları gibi hassas bilgilerin çalınması mümkün hale gelir.

Güvenlik açıkları, özellikle mobil bankacılık ve SMS tabanlı doğrulama sistemleri için ciddi bir tehdit oluşturur.

---

## SS7 ve Modern Telekomünikasyon
SS7, 5G ve VoIP gibi modern teknolojilere geçiş sürecinde yerini kısmen IP tabanlı protokollere bırakmıştır. Ancak, SS7 hala birçok altyapıda aktif olarak kullanılmaktadır ve tamamen ortadan kalkması zaman alacaktır. **Diameter** ve **SIP (Session Initiation Protocol)**, SS7'nin yerini almak üzere tasarlanmış daha modern protokollerdir.

---

## Sonuç
SS7, telekomünikasyon sistemlerinin temelini oluşturan kritik bir protokoldür. Ancak, güvenlik açıkları nedeniyle günümüzde önemli riskler barındırmaktadır. Telekomünikasyon operatörlerinin SS7 altyapılarını güncellemesi ve ek güvenlik önlemleri alması gerekmektedir. Protokolün yerini alacak yeni teknolojiler geliştirilse de SS7'nin tarihi önemi ve mevcut kullanım alanları göz ardı edilemez.

---

## Kaynakça

1. ITU-T. (1993). "Q.700: Introduction to CCITT Signalling System No. 7."
2. Meyer, D., & Weiss, R. (2017). "SS7 Exploitation and Mitigation Strategies." IEEE Communications Magazine.
3. "Signaling System No. 7 (SS7) Basics." Cisco Systems, White Paper.
4. U. Fayyad, & R. Uthurusamy. (2018). "SS7 vulnerabilities: Current landscape and future directions." Journal of Network Security.
5. NIST. (2020). "SS7 and Diameter Security Guidelines."

