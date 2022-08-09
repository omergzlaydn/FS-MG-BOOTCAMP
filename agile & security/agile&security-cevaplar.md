## Agile & Security Cevaplar

// 1.soru 

Encoding

Verileri kodlamak, verileri bir şema kullanarak yeni bir biçime dönüştürmeyi içeren bir işlemdir. Kodlama tersine çevrilebilir bir işlemdir; veriler yeni bir biçime kodlanabilir ve orijinal biçimine göre çözülebilir. Kodlama genellikle kolayca tersine çevrilebilen herkese açık bir şema içerir. Kodlama verileri genellikle verilerin bütünlüğünü ve kullanılabilirliğini sağlamak için kullanılır ve veriler sistemler veya uygulamalar arasında geçerli biçimde aktarılamadığında yaygın olarak kullanılır.

Kodlama, verileri korumak veya korumak için kullanılmaz, çünkü tersine çevrilmesi kolaydır.

Bir kodlama örneği şöyledir: Base64

Bir kullanıcının bir iş başvurusu web sitesine özgeçmiş yüklemek istediği ve web sunucusunun depoladığı bir senaryoyu ele alalım


Hashing

Karma, verilerin sabit uzunlukta matematiksel bir özetini hesaplamayı içerir, giriş verileri herhangi bir boyutta olabilir. Kodlamanın aksine, karma işlemi tersine çevrilemez. Bir karma alıp orijinal verilere geri dönüştürmek mümkün değildir. Karma, genellikle sağlama toplamı olarak adlandırılan verilerin bütünlüğünü doğrulamak için yaygın olarak kullanılır. Aynı karma işlevi kullanılarak iki özdeş veri parçası karma hale getirilirse, elde edilen karma aynı olacaktır. İki veri parçası farklıysa, ortaya çıkan karmalar farkl-ı ve benzersiz olacaktır.

Örnek olarak, Ali'nin Burak'a bir dosya göndermek istediğini ve Burak'aın tam olarak aynı dosyaya sahip olduğunu ve aktarma işleminde herhangi bir değişiklik olmadığını doğrulayın. Ali, Burak'a dosyanın bir karmasıyla birlikte dosyayı e-postayla gönderir. Burak dosyayı indirdikten sonra, dosya üzerinde bir karma işlevi gerçekleştirerek dosyanın aynı olduğunu doğrulayabilir ve elde edilen karmanın Ali'nin sağladığı ile aynı olduğunu doğrulayabilir.

Karma işlevin bir örneği şudur: SHA512

Karma, verilerin bütünlüğünü doğrulamanın yanı sıra, bilgisayar sistemleri ve uygulamaları için kimlik doğrulama işlemlerinde önerilen veri dönüştürme tekniğidir. Parolaları asla saklamamanız ve bunun yerine yalnızca “tuzlanmış parola(güvenlik katmanı oluşturur)” nın karmasını saklamanız önerilir. Salt, yalnızca kimlik doğrulama işlemi sisteminin bildiği bir parolaya eklenen rasgele bir dizedir; Bu, iki kullanıcının aynı parolaya sahip olması durumunda depolanan karmaların farklı olduğunu garanti eder.

Bir kullanıcı bir web uygulamasına parola girdiğinde, parola web sunucusuna gönderilir. Web sunucusu daha sonra parolaya tuz ekler ve parola ve tuz üzerinde bir karma işlevi gerçekleştirir ve bu çıktı karmasını kullanıcı için veritabanında depolanan karma ile karşılaştırır. Bu kullanıcı için karmalar eşleşirse, kullanıcıya erişim izni verilir. Karma, bir ihlal veya kötü niyetli içeriden birinin olması durumunda orijinal şifrelerin asla alınamamasını sağlar. Tuzlama, bir ihlal meydana gelirse, saldırganın hangi kullanıcıların aynı şifrelere sahip olduğunu belirleyememesini sağlar.

Encryption

Şifreleme, verileri yalnızca anahtarı veya şifresi olan yetkili kullanıcıların orijinali ortaya çıkarmak için verilerin şifresini çözebileceği şekilde güvenli bir şekilde kodlama işlemidir. İki temel şifreleme türü vardır; simetrik anahtar ve ortak anahtar. Simetrik anahtar'da aynı anahtar, parola gibi verileri şifrelemek ve şifresini çözmek için kullanılır. Ortak anahtar şifrelemesinde, bir anahtar verileri şifrelemek için kullanılır ve verilerin şifresini çözmek için farklı bir anahtar kullanılır.

Şifreleme, verilerin korunması gerektiğinde kullanılır, böylece şifre çözme anahtarı olmayanlar orijinal verilere erişemez. Veriler HTTPS üzerinden bir web sitesine gönderildiğinde, ortak anahtar türü kullanılarak şifrelenir.

Şifreleme, verilerin kodlanmasını içerse de, ikisi birbiriyle değiştirilebilir terimler değildir, şifreleme her zaman güvenli bir şekilde kodlanmış verilere atıfta bulunurken kullanılır. Kodlama verileri yalnızca güvenli bir şekilde kodlanmayan veriler söz konusu olduğunda kullanılır.

Şifreleme örneği: AES 256

2.soru 

bu zafiyet hakkında raporu mu hazırlar sonrasında öncelikle birebire kendisiyle konuşmaya çalışırım daha sonrasında ekip önüde zafiyet için hazırladığım raorun sunumunu yaparım 

Güvenli olmayan Doğrudan Nesne Başvuruları (IDOR), bir uygulama kullanıcı tarafından sağlanan girdiye dayalı nesnelere doğrudan erişim sağladığında ortaya çıkar. Bu güvenlik açığının bir sonucu olarak saldırganlar yetkilendirmeyi atlayabilir ve sistemdeki kaynaklara, örneğin veritabanı kayıtlarına veya dosyalara doğrudan erişebilir. Güvensiz Doğrudan Nesne Başvuruları, saldırganların bir nesneye doğrudan işaret etmek için kullanılan bir parametrenin değerini değiştirerek yetkilendirmeyi atlamasına ve kaynaklara doğrudan erişmesine olanak tanır. Bu tür kaynaklar, diğer kullanıcılara ait veritabanı girişleri, sistemdeki dosyalar ve daha fazlası olabilir. Bu uygulama kullanıcı tarafından sağlanan girdi alır ve yeterli yetkilendirme denetimleri gerçekleştirmeden bir nesneyi almak için kullandığı gerçeğinden kaynaklanır.

3. soru

Başarılı proje yönetimi tekniklerinden biri de Scrum’dur. Scrum, Agile proje yönetimi metotlarından biridir. Karmaşık yazılım projelerinin başarı oranını yükseltmek için oluşturulmuştur. En yaygın kullanılan proje yönetim metotlarından biridir.

Scrum, projeyi küçük parçalara ayırarak yönetmeyi önerir. Bu sayede her parça tek tek incelenip gerekli değişiklikler yapılabilir. Bir parçada olan sorun daha kolay bulunabilir. Scrum’a göre proje yönetilirken müşteri ile daima iletişim halinde olunması gerekir. Scrum’un projeyi küçük parçalara ayırmasındaki en temel sebeplerden birisi, müşterilerin isteklerine göre projenin şekillendirilmesini kolaylaştırmaktır.

Scrum 3 temel üzerine oturtulmuştur:

-Şeffaflık
-Kontrol edilebilme
-Uyumluluk

Scrum, bir projenin şeffaf şekilde yönetilmesini savunur. Projenin her aşaması, hem çalışanlar hem de müşteriler tarafından bilinmelidir. Böylece müşterinin talep edebileceği tüm değişiklikler hızla gerçekleştirilebilir. Müşteri, çalışmanın her aşamasına müdahale ederek hayalindeki yazılıma kavuşacak ve proje başarıyla sonuçlanacaktır.

4.soru

-Repository Proje dosyalarını uzak bir sunucuda depolar. Genel kullanımda “Repo” olarak da kısaltılır.
-Branch Projenin bir çok bölümünü derli toplu şekilde tutulmasını sağlar. Branchin avantajı ana branchteki(master) geliştirme yapısını etkilemeden projeyi diğer oluşturduğumuz branchler üzerinden yönetebiliriz.
-Commit Proje dosyalarınızda belli bir değişiklik yaptığınızda o değişikliğin anlık görüntüsünün alınıp kaydedilmesine denir.
-Fork Repository’nin bir kopyasının alınmasıdır. Temel anlamda forkun kullanım amacı alınan bu kopya üzerinde değişiklikler yaptıktan sonra projenin ana reposuna gönderilerek projenin gelişmesine katkı sağlamaktır.
-Pull Request (PR): Fork edilen proje üzerinde değişiklikler yaptıktan sonra gerçek repository’e gönderilerek o projenin sahibi olan geliştiricinin değerlendirmesine sunmaktır. Eğer PR kabul edilirse ana repository üzerinde, fork ettiğiniz proje üzerinde değişiklikler işlenir.
-Merge Branch üzerinde yaptığımız değişiklikleri master branch’i üzerinde birleştirme işlemidir.
-git push : Commit’lediğimiz dosyaları uzak sunucudaki repository’e gönderir.

5. soru
branch last commit nedir? : değişikleri geri alır
Repository last commit nedir? : çalışmanın sonu kaydetme aşaması

6.soru
SQL veritabanları tablo tabanlıdır, NoSQL veritabanları ise belge tabanlı, grafik veritabanları, geniş sütun depoları veya anahtar-değer çiftleridir. Yapılandırılmış sorgu dili aslında SQL'in (Structured Query Language) adını aldığı yerdir. NoSQL DB'de, sorgulara odaklanmak ve belge toplamadır.

