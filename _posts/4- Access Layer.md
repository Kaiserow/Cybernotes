# Ethernet Frame

Ethernet teknolojisinin  WLAN'ler (Wired Local Area Network) için kullanıldığını daha önce söylemiştik. Cihazlar WLAN'deki iletişimlerini NIC'ler (Network Interface Card) sayesinde yaparlar. Her Ethernet NIC'i kendine özgü ve kalıcı MAC (Media Access Control) denilen adreslere sahiptir. Bu MAC adresleri kaynak ve hedef MAC adresleri olmak üzere Ethernet Frame'nin içinde "Field" olarak adlandırılan alanlarda bulunur.


![Image](images/ethernet-frame-format.png)

Yukarıda gördüğünüz her bir field (yani alan) ayrı ayrı görevlere sahiptir. Her birinden genel olarak bahsedelim;

## Preamble

Bu alanın temel amacı alıcıyı veri alımına hazırlamaktır. Alıcının veri alımına hazır olup olmadığı kontrol ederken aynı zamanda alıcının sinyal saatini senkronize etmesini sağlar.

## Start Frame Delimiter (SFD)

Veri çerçevesinin başladığını alıcıya bildiren alandır yani Ethernet Frame'nin başlangıç noktasıdır.

## Destination MAC Address

Veriyi gönderdiğimiz NIC'in MAC adresini içerir. Hedef MAC adresi daima kaynak MAC adresinden önce yer alır. Bunun nedeni ağ içinde ilgili portlara yönlendirme yapan switch gibi bir cihazın ilk olarak hedef MAC adresine bakması ve ona göre hedef porta yönlendirmesidir. Sadece switch değil, Ethernet Frame'nin tüm alıcıları ilk önce hedef MAC adresine baktığından, kaynak MAC'ten önce yer alır.

## Source MAC Address

Kaynak NIC'in MAC adresini içerir. Bu sayede Ethernet Frame'nin hangi NIC'ten geldiği anlaşılır.

## Length/Type

Yukarıdaki resimde "802.3 Ethernet Frame" diye belirtildiği dikkatinizi çekmiş olabilir. Bunun ayrıca belirtilmesinin sebebi 802.3 Ethernet Frame'inden sonra bir de günümüzde çok daha yaygın olarak kullanılan Ethernet II Frame'nin çıkmış olmasıdır. 802.3 Frame'i daha eskide kalmış olup bu çerçevenin içindeki "Length" alanı veri uzunluğunu belirtir. Bu veri uzunluğu sadece "Data" alanındaki verinin uzunluğudur. Ethernet II Frame'inde length alanı yerine "Type" alanı kullanılır. Type alanı, üst katman protokolünü belirtir. Hangi ağ iletişim modeline bakarsanız bakın her ikisinde de -Ethernet Frame'i OSI modeline göre "Data Link Layer'da" TCP/IP modeline göre "Network Access Layer'da" çalışır- bir üst katmanın Network ya da diğer adıyla Internet katmanı olduğunu görebilirsiniz. Dolayısıyla type kısmının bir üst katmanda çalışan IPv4-v6, ARP gibi protokolleri belirttiğini söyleyebiliriz.

## Data

Çerçevenin payload kısmıdır, iletilen asıl veriyi içerir. Bu kısım daha üst katman protokollerin verilerini taşıdığından bir "Header" kısmına sahip olabilir.


#### NOT: Header'ın ne olduğu daha sonra anlatılacaktır.

## Frame Check Sequence (FCS)

Bu alan verilerin iletiminin doğruluğunu sağlamak için hata denetim mekanizması sağlar. 














