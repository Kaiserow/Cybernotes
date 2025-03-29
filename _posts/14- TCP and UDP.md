# TCP and UDP 

Bu protokoller transport layer protokolleridir ve en genel manada segmentlerin kaynaktan hedefe nasıl gideceğini belirler. UDP, daha çok real-time iletişimler için kullanılır. Bunun sebebi datagramları olduğu gibi ve kontrol mekanizması olmadan iletmesidir. Böylece gecikmenin önüne geçilerek gerçek zamanlı iletişimler daha verimli sağlanır. Örneğin bir video izlerken UDP kullanılması daha verimli olabilir, aksi halde çok fazla donmalar olacaktır. Fakat UDP'nin bir kontrol mekanizmasının olmaması da veri kaybına yol açabilir ve verilerin bir kısmı iletilirken kaybolabilir.

Bunun yanında banka işlemleri ve para transferi gibi verinin kaybolmasının çok daha tehlikeli olduğu iletişimlerde TCP tercih edilmelidir. Bunun sebebi ise TCP'nin "reliability"e dayanan yani güvenilir bir protokol olmasıdır. Bu, iletilen segmentlerin tam olarak karşı tarafa iletilip iletilmediğini kontrol ettiğini ve eğer eksik segment varsa da tekrar gönderilmesi gerektiğini garanti ettiği anlamına gelir.

Hem UDP hem de TCP iletimlerini kaynak ve hedef port numaralarına göre yapar. Bu port numaraları uygulamadan uygulamaya değişiklik gösterecektir. Ayrıca kaynak port olarak da sizin işletim sisteminizden çıkacak olan portlar da farklı sayılarla ifade edilir. Fakat buna ek olarak TCP segmentlerinde bir de "Sequence Number" adı verilen sıra numaraları bulunur. Bu numaralar sayesinde segmentler hedefe ulaştığında doğru sıraya konulabilir ve ayrıca kaç numaralı segmentin veya segmentlerin eksik geldiği belirtilebilir.

# Port Numbers

Çoğu zaman hem server hem de client tarafında birden fazla uygulama çalışır. Bir client, serverin belirli bir uygulamasına erişmek istediğinde port numaraları sayesinde sadece ilgili uygulamayla iletişime geçebilir. Örneğin, bilgisayarımızdan bir server üzerinde çalışan web sitesine erişmek isteyelim. Bilgisayarımızda aynı anda birden fazla iletişim gerçekleştiğinden sırf bu iletişime özel ayrıca bir port numarası gerekir ki diğer iletişimlerle karışmasın. Bu örnek için işletim sistemimiz 5305 portunu kullanıyor olsun. İlgili web serverındaki sitenin yazılımına erişmek için de 80 portunu kullanmamız gerekir. Çünkü 80 portu sabit olarak bir HTTP portudur ve  web serverından web sayfası almamıza olanak tanır. Kaynak 5305 portundan web serverının 80 portuna bağlanılır ve web sayfası elde edilerek tarayıcımızda görüntülenir. 

## TCP and UDP Port Numbers

Bir serverın verdiği hizmetlerden yani uygulamalardan yararlanmak için onun hangi servisini talep ettiğinizi belirtmeniz önemlidir. Bu yüzden belirli aralıklardaki portlar sabit olarak server uygulamaları için kullanılır. Bunun yanında çeşitli özelliklere sahip farklı aralıklar da bulunur. Port numaralarını atayan ve yöneten kuruluş ICANN yani Internet Corparation Assigned Names and Numbers, portları 1-65,535 arasında 3 farklı kategoriye ayırmıştır. Bunlar şu şekildedir;

### Well-Known Ports

Bunlar çeşitli uygulamaları temsil etmek için kullanılan portlardır. (Örneğin; HTTP -> 80, FTP -> 20 gibi) 1-1023 arasında değer alırlar.

### Registered Ports

1024 ile 49151 arasında değer alan bu portlar, genellikle organizasyonların belirli uygulamaları için kayıt ettirdiği portlardır.

### Private Ports

49152 ile 65535 arasında olan portlardır. Genelde kaynağın kullandığı portlardır. Yani örneğin işletim sisteminin kullandığı portlar olabilir. Herhangi bir uygulama için kullanılabilir.


## Socket Pairs

Source ve destination portları bir segmentin (TCP) ya da datagramın (UDP) içine yerleştirilir. Bunlar da daha sonra source IP ve destination IP bilgisi içeren IP paketlerine kapsüllenir. İşte tam olarak, source IP ve source port ya da destination IP ve destination port kombinasyonuna "Socket" denir. Bunların dördünün de bir araya gelmesi "Socket Pair" kavramını oluşturur. Aslında socketlar, bir sunucunun kimliğini (yani hangi sunucu olduğunu) ve onun sunduğu hizmetlerden hangisinin ilgili hizmet olduğunu belirtmek için kullanılır. Örneğin, 192.168.1.7 adresli serverdan web sayfası hizmetini talep edeceksem socketim 192.168.1.7:80 şeklinde olmalıdır. Socketlar, sadece serverlar için de değil aynı zamanda işletim sistemlerinde de aynı görevi görürler. Yani, 192.168.1.5 hostu tanımlamak için kullanılır ve serverdan spesifik bir hizmeti tanımlamak için de 1099 portunu kullanabilir ve socket "192.168.1.5:1099" şeklinde olabilir. Bu socketlar sayesinde ilgili hizmet doğru şekilde talep edilir ve iletişimlerin karışması önlenmiş olur.

Bilginiz olmadan açılmış TCP bağlantıları güvenliğiniz için ciddi bir tehdit oluşturabilir. Bu durum, bir şeyin ve birinin hostunuza bağlı olduğunu gösterebilir. Bu yüzden komut satırında "netstat" komutu ile mevcut TCP bağlantılarını gözlemleyebilirsiniz.

















#### NOT: TCP, UDP ve port numaraları ile ilgili daha fazla ayrıntı ileride işlenecektir.

