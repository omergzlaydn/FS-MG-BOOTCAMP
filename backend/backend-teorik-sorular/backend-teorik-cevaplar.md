# Backend Teorik Cevaplar
1 .soru 
 GET methodu kullanıldığında istekler URL kısmında gönderilir. Gönderilen bilgiler URL’de görüntülendiği için güvenlik riski yüksektir ancak POST metoduna göre daha hızlıdır.
 /test/demo_form.php?name1=value1&name2=value2

 POST metodu ise URL’de görüntülenmesi istemediğimiz istekler için kullanılır. Gönderilen bilgiler URL’de görünmediği için daha güvenlidir ancak GET methoduna göre daha yavaştır. Yani POST metodunda form alanları HTTP REQUEST HEADER içinde kodlanmış olarak gider, URL’de gözükmez. POST işleminde her türlü dosyayı post edebiliriz: XML,Image, File post edebiliriz.
POST /test/demo_form.php HTTP/1.1
Host: test123.com
name1=value1&name2=value2

GET ile veri göndermede karakter limiti varken POST’ta böyle bir limit yoktur. Karakter limiti GET metodunda 2048 karakterdir.

GET’i ön plana çıkaran bir farktan bahsedelim. GET ile değişkenler URL’de yer aldığı için sayfayı değişken değerleri kaybolmadan yer imlerine atmak mümkündür. Yani GET ile bir sayfa içeriğini sunucudan almak için tekrar tekrar forma veri girmeye ya da sayfa içi tıklamalar yapılmasına gerek yoktur. Dolayısıyla hazır URL’yi yer imlerine atarak kullanıcı zahmetten kurtarılmış olur. POST’ta ise kullanıcı daha önce geldiği aşamaya(sayfa içeriğine) tekrar varabilmek için forma veri girme ya da tıklama zahmetlerine katlanmak zorundadır.

GET’in POST’a karşı bir diğer dezavantajı şudur: multi-part binary türündeki verilerin gönderimi. “multi-part binary” ile kastedilen şey dosyadır. Örneğin; resimdir. POST ile forma bir resim koyup sunucuya upload edebiliriz. Fakat GET ile bu mümkün değildir.

2.soru

API testinin, çağrı sonucunda response’da iletilen değerin beklenen değerle karşılaştırılması olduğunu görmüştük. Status kodu, response, headers vb. alanlar mevcuttur ve bizim bu alanları beklenen değerler ile karşılaştırmamız gerekmektedir. Örneğin, beklediğimiz status code 200 ise sonucunun da aynı şekilde dönmesini bekleriz.

Postman üzerindeki verilere bakarsak, burada şu anda önemli olan 2 adet alanımız var:

Pre-Request script
Test
Pre-request script alanı API çağrı öncesinde, testler ise çağrı sonrasında çalıştırılır.

4.soru

Öğrenci ile Bölüm arasında bire-çok ilişki vardır. Yani bir öğrencinin bir ve yalnız bir bölümü olur.

Aynı şekilde Ders ile Bölüm arasında ve Öğretmen ile Bölüm arasında da bire-çok ilişki var. Yani her ders ve öğretmen bir bölüme ait olmak zorunda.

Öğrenci ile Ders arasında çoğa-çok ilişki vardır. Yani bir öğrenci birden fazla ders alabilir. Bir dersi de birden fazla öğrenci alabilir. Bu nedenle bu ilişki ögrenci_ders adındaki ayrı bir tabloda ele alındı.

Aynı şekilde Öğretmen ile Ders arasında da çoğa çok ilişki vardır. Yani bir dersi birden fazla öğretmen verebilir. Ve bir öğretmen birden fazla ders verebilir.

5.soru
O(n^n) ifadesini net olarak bulamadım  ama tahmini olarak bu ifade olduğunu düşünmekteyim 

O(N²) — Quadratic Complexity Time Algorithm
Quadratic Complexity input büyüklüğünün karesi ile doğru orantılıdır.

Eğer input büyüklüğü 2 ise, 4 işlem gerçekleşir. Eğer input büyüklüğü 8 ise, 64 işlem gerçekleşir ve bu şekilde devam eder.
