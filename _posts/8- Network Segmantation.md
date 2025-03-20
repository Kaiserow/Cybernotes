# Network Segmentation

Ağ bölümlendirmeyi anlamak için ARP sürecini örnek olarak kullanalım. ARP (Address Resulation Protocol) bir host başka bir host'un ip adresini bildiğinde ama MAC adresine sahip olmadığında onun MAC adresini öğrenmek için broadcast yapmasıdır. Yani IP adreslerini MAC adreslerine çözümleyen bir süreçtir. ARP sürecinden daha sonra ayrıntılı bahsedeceğiz ama şimdilik bu kadar bilmemiz yeterli.

Ağlar bütün olarak fiziksel bir ağdan oluşurken o fiziksel ağ birden fazla alt ağa bölünebilir. Bu özellikle büyük ve çok sayıda cihaz içeren ağlar için elzemdir. Bir cihazdan broadcast yapıldığında o mesajın ilgili ilgisiz tüm cihaza ulaşması ağın trafiğini olumsuz yönde etkileyeceğinden ağ, "Broadcast Domain" olarak adlandırılan alanlara bölünür. Biz bu bölümlendirmeye de genel manada "Network Segmentation" yani ağ bölümlendirme diyoruz. Bir ağ broadcast domainlerine bölündüğü zaman, herhangi bir hosttan gelen broadcast mesajı routerın yönlendirme ayarı kapalı olması sayesinde diğer ağlara yönlendirilmeyerek o domain içinde kalır.


Ağlar fazladan trafik oluşmasını engellemenin yanında cihazların bulunduğu konumlara, fonksiyona ve tiplerine göre de bölümlendirilebilir;

## Location

Örneğin bir şirket binasının her katına ayrı bir alt ağ oluşturulabilir ve böylece sadece o kattaki cihazlar o katla ilgili ağa bağlanır.

## Function

Admin erişimi gerektiren cihazlar için ayrı bir ağ oluşturulurken, insan kaynakları ve muhasebe gibi departmanların her biri için ayrı ayrı alt ağ da oluşturulabilir. Böylece ilgili cihazlara sadece o cihazlara erişimi olan kişiler erişebilir ve güvenlik sağlanabilir.

## Device Type

Sadece bilgisayarlardan oluşan bir alt ağ ve bunun yanında serverler ile sadece yazıcıların bulunduğu farklı alt ağlar da oluşturulabilir. 

Bu bölümlendirmelerin hepsi çeşitli görevler ve güvenlik için gerekebilir.
