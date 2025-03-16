Aynı insanların birbiri ile olan iletişimleri gibi cihazların da birbiri ile iletişime geçtiğini biliyor olabilirsiniz fakat bunun nasıl gerçekleştiğini hiç merak ettiniz mi?
İnsanları birbirine bağlayan konuşma dilleri gibi ağlar da cihazları birbirine bağlayarak iletişime geçmesine olanak tanırlar. Nasıl insanlar iletişime geçmek için konuşma dillerine ihtiyaç duyuyorsa cihazlar da ağlara ihtiyaç duyarlar. Günümüzde cihazların birbiri ile iletişime geçmesinin tek yolu ağlar olmasa da en yaygın olarak kullanılan yöntemdir. Bu yüzden ağların nasıl işlediğini ve çalıştığını öğrenmek, siber güvenliğin en temelidir diyebiliriz. Siber güvenlik serüvenine bu en temel noktadan başlamak, üstüne inşa edeceğiniz bilgilerin mantık çerçevesine oturmasına olanak tanıyacaktır.

Günümüzde "Internet" kavramı "inter connect" yani "ağlar arası bağlantı" kavramından gelmektedir. İnternet, birden fazla devasa ağı birbirine bağlayarak insanları ve aynı zamanda da cihazları ortak bir noktada iletişime geçmesine olanak tanır. Peki ya internetin birbirine bağladı diğer ağlar nelerdir?


Local Networks

Şimdilik kafa karışıklığı olmaması açısından sadece Local network'lerden bahsedelim. Local yani yerel ağlar, 1-2 cihazdan oluşan ev ağları olabileceği gibi sayılarının 100'ü aştığı cihazların bulunduğu ağlar da olabilirler. Buradaki önemli nokta cihaz sayısı değil, yerel ağların sadece yerel bölgede kaldığı, dışarıya açıldığında artık ona yerel demememiz gerektiğidir. Yani yerel ağ; okul, ofis, ev, fabrika gibi belirli bir coğrafi konumda bulunan cihazları birbirine bağlayan bir ağ türüdür.

Ağların cihazlar arasındaki iletişimi sağladığını öğrendik. Şimdi ise gelin bunu en temelde nasıl sağladığına bakalım.

Binary Digit (Bit)

------------
------------

Bandwidth & Throughput

Bandwidth bir ağda maksimum taşınabilecek veri miktarını yani o ağın kapasitesini ifade ederken throughput ise o ağda belirli bir süre içerisinde gönderilen ve alınan veri miktarını temsil eder. Bir su borusu düşünecek olursak bu borunun su taşıma kapasitesi bandwith'i, içinden geçen su miktarı ise throughput'u temsil eder diyebiliriz. Bunlara ek olarak bir çok online oyunda rastlamış olabileceğiniz ve ms (milisecond) olarak ifade edilen, bir verinin kaynaktan hedefe gönderilip tekrardan kaynağa dönmesi sırasında geçen süreye de "Latency" yani gecikme diyoruz. Bu da basit olarak suyun, borunun bir ucundan diğer ucuna gitme süresiyle örneklendirilebilir.


Host, Client ve Server Kavramları

Network'e bağlı olan ve bu ağdaki iletişime doğrudan katılan bir cihaza host denir ve bu hostlar ağ içerisinde veri gönderip veri alabilir. Ağ iletişiminde client ve serverin rolünü anlamak için öncelikle cihazların ve en nihayetinde son kullanıcı olan bizim neden böyle bir iletişime ihtiyaç duyduğumuzu anlamamız gerekir. Serverler yani sunucular cihazlara ve/veya insanlara kendi üstünde barındırdıkları belirli başlı hizmetler sunarlar. Örneğin server kendi üstünde bir web sayfası çalıştırıyor ve bunu hizmet olarak sunuyor olabilir. Biz de cihazımızla beraber bu hizmetten faydalanmak istersek bu sunucuya bir istekte bulunarak web sayfasını görüntüleyebiliriz. Bu noktada bize bu hizmeti sunan cihaz server (sunucu) bu hizmetten faydalanan bizim cihazımız ise client (müşteri, alıcı) olarak adlandırılır. Günümüzdeki ağlarda bir çok cihaz aynı anda hem client hem de server olarak kullanılabilir.

Peer to Peer (P2P) Networks

Yukarıda bir cihazın aynı anda hem client hem de server olarak çalışabileceğinden bahsetmiştik. İşte tam olarak bu şekilde çalışan cihazların olduğu ağa "Peer to peer" networkler diyoruz. P2P ağının kurulumu çok daha basittir ayrıca hali hazırda cihazlar zaten server olarak davranabildiğinden ekstra server kurma uğraşı ve maliyeti ortadan kalkar. Ek olarak P2P ağının dosya paylaşımı gibi basit işler için elverişli olduğunu söyleyebiliriz. Fakat bir cihazın aynı anda hem client hem de server olarak davranması özellikle de büyük ağlarda ciddi bir trafiğe yol açarak ağın yavaşlamasına sebebiyet verir. P2P ağları her cihazın kendi arasında iletişimine olanak tanıdığından merkezi bir cihaz tarafından yönetilmez ve bu yüzden de çeşitli güvenlik riskleri ortaya çıkar.

Network Infrastructure

Bir verinin kaynaktan hedefe gitmesi için arada bir çok çeşitli cihazdan geçmesi gerekir. Bu cihazları şöyle sınıflandırırız;

End Devices -> Bilgisayarlar, mobil telefonlar, IP telefonlar, yazıcılar vb. Yani kısaca son kullanıcı cihazları diyebiliriz.

Intermediary Devices -> Router, switch gibi aracılık sağlayan cihazlar.

Network Media -> Wireless (örneğin radyo frekanslarının kullanıldığı ortamlar) yani kablosuz ortamlar olabileceği gibi bakır ve fiber optik kablolar da verinin taşınmasına olanak tanıyan ortamlardır.

Bunlar genel olarak bir ağın fiziksel olarak alt yapısını oluşturan donanımlardır.

ISP (Internet Service Provider) Nedir?

İnternet servis sağlayıcıları yerel ağlarlarla interneti birbirine bağlayarak bunun hizmetini kullanıcılarına sunan kuruluşlardır. ISP'ler bir çok büyük ağı birbirine bağlayarak backbone (omurga) görevi görür. Bu büyük ağları backbone ağlara yüksek hızlarda bağlayabilmek için fiber optik kablolar tercih edilir. Fiber optik kablolar iletim için ışığı kullandığından çok daha yüksek hızlarda veri aktarımı sağlar. Ancak her ağda backbone ağlarda olduğu gibi fiber optik kablolar kullanılmaz. Örneğin bir evdeki ağda coaxial kablo kullanılarak internet bağlantısı televizyon üzerinden sağlanıyor olabilir. Bu bağlantının çalışabilmesi için internet veri sinyalini diğer başka sinyallerden ayırabilen bir modeme ihtiyaç duyulur. Bu yönteme ek olarak internete bağlanmak için DSL (Digital Subscriber Line) de tercih edilebilir. DSL 3 kanaldan oluşan, telefon sinyali ile beraber internet sinyallerini taşımaya olanak tanıyan bir hizmettir. İlk kanalı telefon aramaları için kullanılırken 2. kanalı internetten bilgi almaya (download), 3. kanalı ise internete bilgi yüklemeye (upload) olanak tanır. DSL bağlantılarının hızı telefon hattının kalitesine ve hizmeti aldığınız kuruluşun size olan mesafesine bağlıdır. Daha uzak konumlar daha yavaş bağlantılara sebebiyet verir. Bu bağlantı türlerine ek olarak diğer tercihler şunlar olabilir;

Cellular (Hücresel) Connection

İnternet erişimi için telefon ağlarını kullanan hücresel verinin bağlantı performansı, kullanılan telefon ağının performansıyla sınırlıdır. Sürekli yer değiştiren insanlar için sabit bir internet kullanmak daha zor olacağından hücresel veri bağlantısı tercih edilebilir. 

Satellite Connection

ISP'den gelen sinyali uydu aracılığı ile yansıtarak bağlantı sağlar. DSL ya da başka türlü kablolu bağlantı sağlanamayacak yerlerde tercih edilebilir ancak kurulumu maliyetli olabilir.




