# MAC and IP

## Destination on Same Network

Bazen bir cihaz başka bir cihaza veri iletmek ister ama sadece o cihazın IPv4 adresine sahipken MAC adresini bilmiyordur. 

MAC adresleri aynı ethernet LAN içerisindeki hostların NIC'lerinden NIC'lerine (NIC-to-NIC) iletişim sağlamasına olanak tanıyan adreslerdir. 

IP adresleri ise source device'tan destination device'a iletim yapmaya olanak tanır. Bu iletim aynı yerel ağ içerisindeki hostların iletişimi olabileceği gibi aynı zamanda farklı bir ağdaki hosta da iletim sağlanması söz konusu olabilir.

MAC adresleri fiziksel adreslerdir ve aynı ağ üstünde NIC'ten NIC'e iletilmesi için IP paketlerinin içine kapsüllenirler. Eğer destination (hedef) ip adresi aynı ağ içerisindeyse, destination MAC adresi hedef cihazın NIC'inin adresi olacaktır.

![Image](images/samenetwork.png)

## Destination on Remote Network

Destination ip adresi aynı ağda değil de farklı bir ağda olursa host, ilk olarak routerın local network için olan arayüz adresine yani default gatewaye gideceğinden destination MAC adresi default gatewayin yerel arayüzü olur.

![Image](images/remotenetwork.png)

Bu örnekte de görüldüğü üzere PC1, PC2'ye paket göndermek istediğinde PC2'nin farklı ağda olmasından dolayı ilk olarak default gateway arayüz adresine gitmesi gerekir. Bunu da destination MAC adresini default gateway'in NIC'inin adresini yaparak sağlar. Router bu bilgiyi aldığında Layer 2 bilgilerini de-encapsulate eder ve kendi IPv4 adrelemesini encapsulate ederek eski ip adreslemeyi kaldırır. (yani hostun local ipsi yerine onu dış ağda temsil edecek public ipyi koyar) Sonrasında en iyi yolu tercih edecek şekilde external interfacesinden sıradaki cihaza gönderecektir.

![Image](images/remotenetwork2.png)

Varış noktasında da ilk baştaki aşamalara benzer süreçten geçilir. Aşağıdaki örnek ile bunu yorumlayabilirsiniz.

![Image](images/remotenetwork3.png)

IP'lerden ve MAC'lerden konuşurken akıllara şu soru gelebilir; Hedefe giden yol boyunca tüm bu IP adresleri nasıl bir MAC adresiyle ilişkilendirilir? Tam da bu noktada yazının başındaki ifadeye geri dönüyoruz. IP adreslerinin MAC adresleriyle ilişkendirilmesi IPv4 için "Address Resulation Protocol (ARP)", IPv6 için "ICMPv6 Neighbor Discovery (ND)" protokolleriyle sağlanır. Örneğin bir ethernet local networkünde H1 hostu H2 hostuna bir paket göndermek istiyordur ancak sadece H2'nin ip adresine sahiptir. H1'in bu paketi göndermesi için aynı zamanda MAC adresine ihtiyacı olduğundan, o ağdaki switche destination MAC adresi "ff:ff:ff:ff:ff:ff" olan bir broadcast frame'i gönderir ve switchde bu mesajın geldiği port hariç tüm portlara bu mesajı iletir. Bu frame'i alan tüm cihazlar bunu işler ve kendi NIC'inin MAC adresiyle karşılaştırır. H1 hostunun sahip olduğu ip adresi ile kendi MAC adresi eşleşen H2 hostu "ARP Reply" ile bu süreci doğrular. Yani daha net ifade etmek gerekirse ARP, yalnızca hostun IPv4 adresi bilindiğinde yerel ağdaki bir hostun MAC adresini keşfetmek ve depolamak için şu adımları izler;


Gönderen host, broadcast MAC adresine adreslenmiş (broadcast MAC -> ff:ff:ff:ff:ff:ff) bir frame oluşturur ve gönderir. Bu framede, hedeflenen hostun IPv4 adresine sahip bir mesaj bulunur. Ağdaki her host, broadcast frame'ini alır ve mesajdaki IPv4 adresini yapılandırılmış IPv4 adresiyle karşılaştırır. Eşleşen IPv4 adresine sahip host, MAC adresini kaynak hosta geri gönderir. Kaynak host, mesajı alarak MAC adresi ve IPv4 adresi bilgilerini ARP tablosu adı verilen bir tabloda depolar. Eğer kaynak host ARP tablosunda veri göndermek istediği destination hostun IP adresine karşılık MAC adresini kaydetmişse, broadcast yapmak yerine direk olarak o hosta veriyi iletecektir.
