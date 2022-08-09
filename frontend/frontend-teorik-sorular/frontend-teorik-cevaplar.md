# Frontend Teorik Cevaplar

1. soru cevap
- let-const arasındaki farklar
const ile oluşturulan bir değişkene daha sonrasında tekrar değer ataması yapılamaz.

- let ile oluşturduğumuz bir değişkene daha sonrasında yeni bir değer atayabiliriz ancak const ile oluşturulan değişkene yeni bir değer tekrar atanamaz. Bu durum immutable(Değişmez) olarakta tanımlanmaktadır.

- Let ve const block scope özellikli oldukları için herhangi bir şekilde scope dışında kullanılamazlar.

2.soru 
Birden fazla verinin saklanması için oluşturulan değişkenlere dizi adı verilir. Dizilerin oluşturulmasındaki temel düşünce birden fazla veriye tek bir değişken altından erişebilmektir.

Değişkenlerdeki her bir veriye eleman denir. Dizi elemanları indeks değerleri ile çağrılırlar. İndeks bir elemanın dizi içinde nerede yer aldığını gösterir.

İndeksler bir çok programlama dilinde olduğu gibi 0'dan başlar. 0'dan başlamasının sebebi programlama dillerinin tamamen insan mantığı oluşturulmuş olduğunun göstergesidir.

Dizide eleman tanımlamak için kullanılan üç yöntem vardır.

<script>
    var sayilar = new Array("sıfır", "bir", "iki", "üç");
    document.write(sayilar);
</script> 

sayilar adında 4 elemanlı bir dizi oluşturduk.


-- length özelliği: Bir dizinin eleman sayısını dilimizde uzunluk anlamına gelen length özelliği ile sorgulayabiliriz.

<script>
    var sayilar = ["sıfır", "bir", "iki", "üç"];
    document.write(sayilar.length);
</script> 

-- push( ) metodu: push dilimizde ittirmek anlamına gelmektedir. JavaScript'te dizinin sonuna eleman eklemek için kullanılır.

<script>
    var sayilar = ["sıfır", "bir", "iki", "üç"];
    sayilar.push("dört", "beş");
    document.write(sayilar);
</script>

-- unshift( ) metodu: Bu method JavaScript'te dizinin başına eleman eklemek için kullanılır. 

<script>
    var sayilar = ["sıfır", "bir", "iki", "üç"];
    sayilar.unshift("eksi üç", "eksi iki", "eksi bir");
    document.write(sayilar);
</script> 

-- delete operatörü: Bu operatör ilgili elemanı listeden çıkartır ve yerine tanımsız bir eleman atar. Diğer bir ifade ile ilgili indekse ait elemanı tanımsız yapar. 

<script>
    var sayilar = ["sıfır", "bir", "iki", "üç"];
    delete sayilar[1];
    document.write(sayilar+"<br>"+sayilar.length);e(sayilar+"<br>"+sayilar.length);
</script> 

3.soru

Ternary Operator
Ternary Operator 3 adet parametre alan tek JavaScript operatörüdür. If kullanarak kontrol etmek istediğimiz koşullarda ternary operator kullanarak satır sayısı olarak avantaj sağlayabiliriz.

Ternary operatörünün aldığı 3 parametre şu şekildedir:

İlk önce bir condition belirtiriz ve sonrasında hemen bir ? koyarız
Sonrasında, eğer yazdığımız condition doğru ise ne yapmak istediğimizi belirtir ve sonuna : koyarız
Ve sıra geldi koşulumuz yanlış ise ne yapmak istediğimize.
eğer yağmur yağıyorsa umbrella dönecek, fakat yağmur yağmıyorsa nothing dönecek.
Yazdığımız condition'nın bize direkt olarak false dönmesinin yanı sıra, aynı zamanda false dönecek diğer ifadeler şunlardır: null, NaN, 0, ""(boş string) ve undefined.


4.soru 
`Promise`

Promiseler, ‘Callback Hell’ durumundan kaçınmak için ve beklenmeyen durumla karşılaşıldığında hata kontrolünün daha rahat yapılabilmesi için geliştirilmiş ES6 olarak bilinen ECMAScript 2015 ile bize sunulan asynchronous bir yapıdır.

Bir promise 3 durumdan oluşur;

Pending: Bu başlangıç aşamasıdır. Bu aşamada bir şey gerçekleşmez. Bu aşama için şöyle düşünebiliriz, müşteri sana bir sipariş verecektir. Ama henüz bir şey sipariş etmemiştir.
Resolved: Bu aşama ise işlemin sonuçlandığı ve başarılı olduğu aşamadır. Yani müşteri siparişini almış ve memnun kalmıştır.
Rejected: Bu aşama ise hata ile sonuçlanan aşamadır. İstenen sipariş gelmemiş ve müşteri restoranı terk etmiştir.

`Async/Await`

Await, hakkında temel olarak bahsedecek olursak sözdizimsel (syntatic) rahatlatıcıdır. Asenkron kodunuzun, anlaşılması daha kolay olan senkron kod gibi görünmesini sağlar.

Rahat okunabilir hale gelecek.
Asenkron işlemlerin gerçekleşme sırasını daha rahat bir şekilde takip edebileceğiz.
Promise zincirlerinde yaptığımızbirçok .then() yazma işlemini yapmamıza gerek kalmayacak.
try-catch yapısı kullanılabilecek.

chainAsync fonksiyonu için “async” anahtar sözcüğünü kullandık. Bu, JavaScript’in async/await sözdizimini kullandığımızı gösterir ve Await’i kullanmak için gereklidir. Await’i global düzeyde kullanamayacağınız anlamına gelir.
Async işlevinde döndürülen tüm sözlerin senkronize edilmesini sağlamak için, bir wait anahtar sözcüğü kullanılır, bu birbirlerini beklemesini sağlar. Await ile .then() ve .catch() içindeki geri aramaların kullanımını ortadan kaldırır.
Söz döndürülürken async kullanılır. Söz çağrılacağı sıra ise await eklenir.
Not: try ve catch bir async fonksiyonun rejection (reddetme) değerini almak için kullanılır.

