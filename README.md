# Yerli Uçuş Kontrol Kartı Tasarımı
## ByteSpark Yazılım Robotik ve Havacılık A.Ş

##### 2019 yılında başlayarak AR-GE’sini yürüttüğümüz ve tamamladığımız Yerli uçuş kontrol kartı tasarımı ve yazılımı 2022 yılında nihai halini bulmuştur. 



https://github.com/ByteSparkYazilim/yerli_ucus_kontrol_karti/assets/145047961/d698ae8f-0ea3-4ec0-9d6d-a05060561080

![resim1](https://github.com/ByteSparkYazilim/yerli_ucus_kontrol_karti/assets/145047961/19ea5555-78a4-433d-a5de-0375e504ebc0)

### 1. Prototip
* 6 motora kadar döner kanatlı hava araçları ve tek motorlu sabit kanat hava araçları için uygundur ve ekibe ait ilk prototiptir. 
* Tasarlanan kart çift katlıdır ve 3S Li-Po pil ile beslenmektedir.
* Tasarımda üstte yer alan güç bölümü, kart üzerindeki elektronik bileşenlerin talep ettiği 5V/3A gerilim ve akımı sağlamaktadır. Voltaj düşürücü olarak LM2596S kullanılmıştır. 
* Kartın besleme girişinde 1 adet 5A sigorta kullanılmıştır.
* BNO055 eksen-ivme sensörü uçuş oryantasyonu için kart merkezinde yer alır. Bununla birlikte kullanılan diğer sensörler BME280 basınç sensörü ve GPS’tir.
* Uçuş yazılımı ARM tabanlı bir denetleyici olan STM32f407VGT6 ile programlanmaktadır. 
* Temel bileşenler dışında kart üzerinde 4 adet led, 1 adet buton, yedek pin olarak 1 aet UART, 1 adet I2C, 1 adet SPI, 1 adet analog çıkış bulunur ve pin soket tipi JST olarak seçilmiştir.

  
##### (2021 yılı Prototipi)
![resim2](https://github.com/ByteSparkYazilim/yerli_ucus_kontrol_karti/assets/145047961/c2752817-7c5b-4334-9616-32fb712f59a9)


### Nihai Tasarım (2022)
##### 2022 yılında uçuş kontrol kartı tasarımı nihai haline gelmiştir. Bu süreçte kartın donanım ve yazılımı sürekli olarak güncellenmiş ve geliştirilmiştir. Nihai tasarımda kartın güç ve kontrol birimi ayrılmıştır.

#### Güç Bölümü
##### Güç bölümü kaynaktan aldığı gerilimi 3 ayrı gerilim seviyesine indirmek üzere tasarlanmıştır:
* İnsansız hava aracının uçuş sırasında su haznesini açabilmesi için su motorunun kullanımı için 12V Inverter
* Kontrol biriminda bulunan ana bileşenler (eksen-ivme sensörü, GPS, haberleşme modülü, kumanda alıcısı, görev bilgisayarı RPi) için 5V Inverter
* Kontrol birimindeki diğer bileşenler (basınç sensörü,SD kart, Kumanda S-bus, Serial-Wire, işlemci) için 3.3V Inverter olarak regüle edilmiştir.
##### Bunun için LM2596S-12V, LM2596S-5V VE AMS1117 lineer regülatörler kullanılmıştır. Pil girişine 5A sigorta yerleştirilerek sistem olası bir akım aşımına karşı korunmuştur.
##### Aşağıda uçuş kontrol kartının güç bölümü şematik gösterimi ve PCB çizimleriyle 3 boyutlu gösterimi verilmiştir.
![resim3](https://github.com/ByteSparkYazilim/yerli_ucus_kontrol_karti/assets/145047961/c9fdf8bf-8fbe-4098-a5ff-1cc1ce672c98)
![resim4](https://github.com/ByteSparkYazilim/yerli_ucus_kontrol_karti/assets/145047961/569b8312-f2d1-4892-89a2-3031e625cf1c)

#### Kontrol Bölümü
##### Aşağıdaki kart kontrol biriminin son prototipidir. Önceki prototiplere kıyasla daha fazla giriş/çıkış pini (I/O)lar bulunmaktadır. Kart 4 katlı olup altıgen şeklinde tasarlanmıştır. 6 motora kadar döner kanatlı araçlar için gerekli olan tüm gereksinimleri karşılar niteliktedir ve geliştirme kartı şeklinde kullanıcı dostu olarak tasarlanmıştır.

##### Yardımcı modüller olarak;
* 4 adet kullanıcı ledi, 
* 1 adet reset  butonu, 
* 1 adet kullanıcı butonu, 
* 1 adet buzzer bulunur.

##### Üzerinde bulunan sensörler haberleşme protokolleri;
* BNMO055 eksen-ivme sensörü, (SPI)
* BME280 VE MS5611 barometrik basınç sensörü, (I2C)
* GPS konum sensörü, (UART)


##### Yedek pinler;
* 1 adet UART
* 1 adet I2C
* 1 adet SPI
* 1 adet ANALOG ÇIKIŞ
 
##### Diğer pinler;
* 6 adet PWM çıkış
* 1 adet SD kart girişi
* 1 adet reset ledi
* Serial-wire girişi
* S-BUS girişi

![resim5](https://github.com/ByteSparkYazilim/yerli_ucus_kontrol_karti/assets/145047961/e1c8ac6c-0f81-4ffe-a183-5d1a72ceeb64)
![resim8](https://github.com/ByteSparkYazilim/yerli_ucus_kontrol_karti/assets/145047961/75c14ab0-2efe-4200-ad84-65a564868cbc)

![resim9](https://github.com/ByteSparkYazilim/yerli_ucus_kontrol_karti/assets/145047961/67dfbe81-259a-488f-bb6e-f916b35dbf1a)








