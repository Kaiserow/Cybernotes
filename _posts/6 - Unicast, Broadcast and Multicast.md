# Unicast

Bir ağ üzerinde veriyi iletmenin farklı yolları vardır. Yalnızca bir cihazdan diğer bir cihaza veri iletimi "Unicast" yani tek noktaya yayın olarak adlandırılır. Unicast bir iletim yapılırken hedef adres genelde unicast adresi olurken bunun yanında multicast veya broadcast adresi de olabilir. Hedef adresin multicast veya broadcast adresi olmasından bağımsız kaynak adres daima unicast adresi olmalıdır. Aksi halde alıcı cihazlar yanıt göndereceği cihazı belirleyemez ve iletişim düzgün sağlanamaz.

Unicast adresleri 1.1.1.1 ile 223.255.255.255 arasında (özel kullanımlar için ayrılmış adresler hariç) değer alabilir. IPv4 adreslerinin maksimum 255.255.255.255'e kadar değer alabileceğini çünkü toplam 32 bitten oluştuğunu belirtmekte fayda var. Yani buna göre özel kullanımlar için ayrılmış adresler hariç neredeyse ağdaki tüm adreslere unicast yapılabilir.

#### Not: Özel kullanım için ayrılan adreslere sonradan değinilecek.

#### Not2: Burada IPv4 adresleri maks. 255.255.255.255'e kadar değer alabilir derken bu adreslerin hepsi bir cihaza atanabilir demediğimi, bunun yerine adres olarak kullanılmasını kastettiğimi belirtmek isterim. çünkü ileride 255.255.255.255 adresinin de "Broadcast" adresi olduğundan bir cihaza atanamayacağını göreceğiz.


# Broadcast

Ethernet switch'i bir hosttan hedef IPv4 adresi 255.255.255.255 olan bir paket aldığında bu paketi kaynak port hariç o ağda mevcut tüm portlara yönlendirir. Böylece ağdaki tüm hostlara bu paket iletilmiş olur. Buna router da dahildir fakat router default ayarlarında bir broadcast başka bir ağa yönlendirmeyecek şekilde yapılandırılmıştır. Routerin bu yapılandırması gereksiz trafiği önleyerek yayının sadece o ağda (daha doğrusu o broadcast domain içersinde) kalmasını sağlar.

#### Not: Broadcast domain, aynı ağ segmentinde bulunan tüm cihazları içerir. Ağlar performans, verimlilik, ölçeklenebilirlik ve güvenlik gibi sebeplerden ötürü çeşitli segmentlere ayrılabilir. Buna da daha sonra değineceğiz.

Broadcast "Directed Broadcast" ve "Limited Broadcast" olarak ikiye ayrılır.

## Directed Broadcast

Adından da anlaşılacağı üzere bir broadcasti spesifik bir ağa yönlendirmeye "Directed Broadcast" denir. Örneğin 172.16.4.0 ağına directed broadcast yapıldığından bahsedecek olursak hedef IPv4 adresi 172.16.4.255 şeklinde o spesifik ağdaki tüm hostları kapsayacak şekilde olmalıdır.

## Limited Broadcast

Bu kavramı anlamak için öncelikle physical network ve logical network kavramlarını doğru şekilde anladığımızdan emin olmamız gerekir. Phsyical network'ün içinde birden fazla logical network olabileceğini ve bunların Physical network'ün alt ağları (subnet) olduğunu tekrardan belirtmek isterim. Directed broadcast spesifik bir alt ağa yapılan bir yayını temsil ederken limited broadcast o fiziksel ağın tümüne yapılan ve hedef IPv4 adresi 255.255.255.255 olan bir yayındır. Kafa karışıklığını gidermek için şu anda broadcast'lerin tümünün belirli bir yerel ağda yapıldığını yani tek bir ağın tümünden ve onun alt ağlarının olduğunu varsaydığımızdan bahsettiğimizi belirtmek isterim.

# Multicast

Bir hostun belirli bir "Multicast" grubuna paket göndermesine olanak tanır. Multicast grubunun alabileceği adres aralığı 224.0.0.0 ile 239.255.255.255 arasındadır. Çoğu durumda (IGMP Snooping yapılmıyorsa ki ne olduğunu bilmemize gerek yok.) bu paketler broadcaste benzer şekilde tüm cihazlara iletilir ama sadece multicast grubuna dahil olan hostlar paketleri işler.





