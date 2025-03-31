# Client and Server Interaction

Server, bir takım bilgiler sunan, sağlayan bir hosttur. Bunun yanında client ise bu bilgileri talep eden, isteyen bir hosttur. Günümüzde server tarafında çalışan birden fazla hizmet bulunur ve bunlardan en yaygın olanları, web, e-mail ile file transfer gibi hizmetleridir. Bu hizmetler için hem client tarafında hem de server tarafında o hizmete özgü yazılımlar çalıştırılır. Örneğin serverda bir web sayfası hizmeti sunmak için web yazılımı çalıştırılırken clientın bunu talep etmesi için "browser" (chrome, firefox vb.) gibi bir client yazılımına ihtiyacı vardır. Bunla beraber çeşitli mailler için serverlarda mail yazılımları çalıştırılırken, client tarafında bunlara erişmek için outlook, gmail gibi client yazılımları kullanılabilir.

## URI, URN, and URL

Bunların hepsi serverda belirli bir kaynağa ulaşmak için kullanılan adreslerdir. 

### Uniform Resource Name (URN) 

Bu protokol bilgisi içermeyen, sadece adını ve yolunu (path) içeren bir gösterimdir.

### Uniform Resource Locator (URL)

Bu da aynı şekilde bir kaynağın ağdaki konumunu tanımlar fakat aynı zamanda protokol de içerir. Bu protokoller HTTP, HTTPS şeklinde olabileceği gibi FTP, SSH şeklinde de olabilir. 

### Uniform Resource Identifier (URI)

Bu ise bir kaynağın tam konumunu tanımlar yani her şey içine dahildir.

![Image](images/The-illustration-of-the-URL-URN-and-URI-26.png)

URI'nin parçaları genel olarak şöyle açıklanabilir;

#### Protocol/scheme 

HTTPS ya da FTP, SFTP, mailto, ve NNTP gibi protokoller.
#### Hostname 

w​ww.example.com
#### Path and file name 

/author/book.html
#### Fragment 

#page155

# FTP (File Transfer Protocol)

FTP protokolü, client ile server arasında dosya aktarımına olanak tanır. Ayrıca clientın uzaktan dosyaları düzenleyebilmesine de olanak tanır. FTP trafiği kontrol edebilmek için ilk önce  21 portundan oturum açmalıdır. Oturum açtıktan sonra dosyaları aktarmak için ise 20 portunu kullanır.

# Virtual Terminals

Telnet veya SSH gibi protokoller belirli bir cihazdan uzaktaki başka bir cihazı kontrol etmeye olanak tanıyan protokollerdir. Örneğin Telnet en eski uygulama katmanı protokollerinden biri olup cihaza, uzaktan metin tabanlı bir kontrol imkanı sunar. Telnet serverleri clientın bu taleplerini 23 portundan dinler. Telnet bunu yapmak için bir "Virtual Terminal" kullanarak, fiziksel olmayan bir CLI yani "Command Line Interface" sunar. Bu komut satırı üzerinden bir cihaza sanki fiziksel olarak bağlıymış gibi komutlar verilebilir.

Yani aslında kısaca telnet, cihazları uzaktan istediğiniz gibi yapılandırmaya, çeşitli dosyaları kaldırıp taşımaya olanak tanır. Bununla beraber Telnet kullanarak ilgili cihaza erişebilmek için giriş yapılması gerekmektedir. Fakat Telnet ile yapılan transferler sırasında veriler şifrelenmez ve düz metin olarak taşınır. Bu verilerin transfer esnasında kolayca ele geçirilip okunabileceği anlamına gelir. Telnetin güvensiz olmasından kaynaklı server erişimleri için iyi bir alternatif olan SSH protokolü tercih edilir. SSH, güçlü bir kimlik doğrulama ile beraber transfer esnasında veri şifrelemesi sunar. Bu yüzden mümkün olan her yerde Telnet yerine SSH kullanılmalıdır.

# Email Clients and Servers

## Simple Mail Transfer Protocol (SMTP)

SMTP, e-mail clientı tarafından onun local e-mail serverına mesaj göndermek için kullanılır. Bu local server, mesajın kendi serverına mı yoksa başka bir servera mı gönderildiğine karar verir. Eğer server bu mesajı başka bir servera göndermeye karar verirse, burda da SMTP protokolü kullanılacaktır. SMTP istekleri 25 portunu kullanır.


## Post Office Protocol (POP3)

POP3 sayesinde kullanıcılara gönderilmiş e-mailler alınır ve depolanır. Ayrıca e-mailin gönderildiği kullanıcı bu e-maile erişmek isterse de POP3 sayesinde erişebilir. E-mailler client tarafından erişildikten sonra POP3 protokolü varsayılan olarak bu e-mailleri sunucudan siler. Böylece bir cihazdan okunan e-mailler başka bir cihazdan erişilemez olur. POP3 serverlerine 110 portundan erişilebilir.

## Internet Message Access Protocol (IMAP4)

Bu da aynı şekilde POP3 gibi kullanıcılara gelen mesajları alır ve depolar. Ama POP'un aksine mesajlar, kullanıcılar tarafından silinmediği sürece serverlarda depolanmaya devam eder. IMAP'in en güncel sürümü olan IMAP4, 143 numaralı porttan gelen istekleri dinlemektedir.



