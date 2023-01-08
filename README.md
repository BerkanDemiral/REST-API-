# REST-API-
# REST API KULLANIMI

Temel tanımını yapmak gerekirse; İki farklı kod parçasının birbirleri ile konuşabilmesi prensibine dayanır

Youtube'a girip video arattığımızda içinde arattığımız kelimelerin geçtiği videolar gelmesi bir nevi API örneğidir.
Ya da klavyede enter tuşuna bastığımızda kodların gönderilmesi de bir API'dır. Burada sürecin nasıl işlediği ile ilgilenmeyiz. Sadece isteğimiz ve isteğimiz sonucunda aldığımız karşılık yani request ile ilgileniriz.  

Örneğin IMDB’de sıralanmış popüler filmleri teker teker yazmaktansa API ile alabiliriz ve bu şekilde üzerlerinde kendi Frontend kodlarımızla harmanlayarak yeni bir proje elde edebiliriz. 

Bir web sitesinin Console kısmında Refresh yaptığımızda aşağıdaki JSON formatlı yapıyı elde ederiz.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fba08993-d580-4fb8-b8d5-748858dbaedf/Untitled.png)

Burada web sitesine bir “REQUEST(İstek)”de bulunuyoruz ve web sitesinden bir “RESPONSE(Yanıt)” elde ediyoruz. Aslında REST API mantığı genel olarak tam da buraya dayanmaktadır. 

!! Burada 2 yapı birbiri ile konuşurken belirli bir kurallar bütününde konuşmaları gerekmektedir. Bunu belirleyen şey bir protokoldür. RESTAPI kullanımında HTTP protokolü kullanılır. Bu protokol ***sunu ile istemci arasındaki iletişimi*** temsil etmektedir.

- Yani özetle, bir http protokolü ile uzaktaki bir sunucuya request(istek) yolluyoruz. O sunucu da aynı protokol doğrultusunda bize response(yanıt) dönüyor.
- Örneğin bir restorana gittik ve yemek söyleyeceğiz. Burada garson bize yemeği getirdi ve yemeği yedik. Yemeğin nasıl yapıldığı ve hangi etin kullanıldığı gibi veriler burada bizi ilgilendirmez. Bizi ilgilendiren kısım isteğimizin(yemek) karşılanmasıdır (yemeğin gelmesi). Burada garson, API Görevi görür.

Burada REST API yapısı ile ilgili çok dikkat edilmesi gereken bir durum vardır. Örneği bir bilgiyi get ederken burada karşıdaki veritabanına direkt erişmiyoruz. Bunun yerine HTTP Protokolüne göre hazırlanmış bir API’yi kullanıyoruz. Bu API sayesinde veritabanından çekilecek bilgilere göre hazırlanmış veriler veri tabanına direkt erişim sağlayacak bir güvenlik açığı oluşturmadan karşı tarafa verilebilmektedir. 

- Ve burada API’nın hangi dil ile oluşturulduğunun hiçbir önemi yoktur. Önemli olan şey http protokollerine uygun olarak yazılmasıdır.

> ***Her Web API bir Rest API değildir ama, her REST API bir WEB API’dir.***
> 

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/dfd25885-9b3e-467b-ade3-6305fc44d070/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bebe6894-6e09-45cc-8c42-c9bd84b5491a/Untitled.png)

- Veritabanına direkt olarak bir müdahale olmaması sayesinde hem güvenlik hem de veritabanının özelinde bozulmaması adına bir konfor oluşturulmuş olur.


## POSTMAN

API Testlerinde sıklıkla kullanılan bir HTTP istemcisi(client)’dir. Uygulama henüz geliştirme aşamasındayken gelecek olan verileri burada test edebiliriz. Eğer direkt url çubuğuna gerekli adresi yapıştırırsak karışık bir json formatı alırız. Burada her yapı daha düzenlidir.

## REST PRENSİPLERİ (KISITLAMALARI)

1. **İstemci Sunucu (Client - Server) Modeli**
    
    İstemci requesti gönderen, sunucu ise çoğunlukla JSON formatında bir response gönderdiği formata dayanır. İki tarafın da net olarak verilerin nasıl alındığı ile ilgili bilgileri yoktur. 
    
2. **Uniform Interface**
    
    Aynı kaynağa gönderilen tüm istekler, isteğin nereden geldiğinden bağımsız olarak aynı şekilde görünmelidir.
    
    ***AYNI URI FAKAT FARKLI METHODLAR FARKLI SONUÇLAR(Parametreli paramteresiz gibi)***
    
    `…./users(get)`
    
    `…./users/11/comments(get) — 11 id’li kullanıcıya ait yorumlar` 
    
    ** İstemci verileri nasıl parse edeceğini bilmelidir ve bu gelen veriyi alırken değiştirebilir. 
    

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7415dbbe-e2e4-4c90-8482-0f330f26d085/Untitled.png)

1. **Durumsuzluk (Statelessness)**
    
    Yapılan her istekler birbirinden bağımsızdır. 
    
    Yapılan her istekte, giriş anahtarının belirtilmesi gerekir. İsteğin gerektirdiği tüm bilgilerin belirtilmesi gerekir. 
    
2. **Cashable (Örneklenebilirlik)**
    
    Cash Bellek bir nev-i ihtiyacımız olan bilgilere daha çabuk erişebilmek için işlemciye yakın bir yere kaydederek daha hızlı erişmemizi sağlayak bir cash klasöründen erişmemizi sağlayan bellektir.
    
    Client direkt sunucu ile iletişime geçmeyebilir. Arada, çok fazla isteği dengeleyip hızlı cevaplar verilmesini sağlayan balance katmanı ya da proxy gibi katmanlar bulunabilir. 
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8f7fcef6-9061-4735-abb8-c2ca02b679ee/Untitled.png)
    

1. **İsteğe Bağlı Kod**
    
    Sunucu istemciye extra kodlar gönderebilir, isteğe bağlıdır.
    
## HTPP NEDİR

**İstemci ve sunucu arasında veri akışının kurallarını belirleyen protokoldür.** 

- Waka şeklinde farklı protokoller de vardır. Sadece HTTP kullanılması zorunluluğu yoktur.

 

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a3b8db1b-3ef7-477c-81f9-7148d4924491/Untitled.png)

- Boşlukların amacı header ve body’i birbirinden ayırmaktır.

## HTTP DURUM KODLARI

Sunucu tarafından ilgili isteğin sonucunu belirten sayısal ifadelerdir. 

Bir nev-i örneğin MVC de site tasarlarken aldığımız cevaba göre kullanıcıya farklı ErrorPage’ler yöneltmemizi sağlayan alandır. 

Hata kodları ilk kodlarına göre gruplandırılabilirler.

**Informational responses (Bidirimsel cevaplar) (100–199)**

- **100** Continue
- **102** Processing —> istek sunucu tarafından alındı ama hala bir dönüş yok

**Successful responses (Başarılı cevaplar) (200–299)**

- **200** OK
- **201** Created —> Sunucu tarafında yeni bir kaynak oluşturulur
- **204** No Content —> Örneğin kullanıcı silindi. Bir body dönmez

**Redirections (Yönlendirme cevapları) (300–399)**

- **300** Multiple Choice —> Farklı uzantılı dosyalar için
- **301** Moved Permanently —> Kaynak adresinin kalıcı değiştirldiğini belirtir. Yeni kaynak body’de belirtilir.
- **304** Not Modified —> Genelde önbellek amaçlı kullanılır. Cashdeki cevabı verdi.

**Client errors (İstemci Hataları) (400–499)**

- **400** Bad Request —> Yeni kullanıcı için eksik parametre verirsek bu hata gelebilir.
- **401** Unauthorized —> Gerekli kimlik doğrulaması yapılamamıştır.
- **403** Forbidden —> Yetkimiz olmayan bir işlemi yapmamız gerekiyordur.
- **404** Not Found —> O An için bulunmayan bir kaynağa erişmek istedik.
- **405** Method Not Allowed

**Server errors (Sunucu Hataları) (500–599)**

- **500** Internal Server Error —> Sunucu istenilen cevabı veremiyordu
- **503** Service Unavailable —> Sunucuda bir bakım vs. varsa bu dönebilir.

## HTTP METHODLARI

**GET**

- Verileri almak - listelemek için kullanılan istek metodudur.

**POST**

- Belirli bir kaynağa veri göndermek için kullanılır.

**PUT**

- Belirli bir kaynaktaki verinin tamamının değiştirilmesi için kullanılan metodtur.
- Sadece yaşı değiştirmek istesek bile diğer alanlara ait verileri de göndermek zorundayız. Where komutunun doğru karşılanması için.
- `{ “name": "Gurcan", "age": 40}`

**PATCH**

- Belirli bir kaynaktaki verilerin bir kısmının değiştirilmesi için kullanılan metodtur.
- `{ "name": "Gurcan"}`

**DELETE**

- Belirli bir kaynaktaki verilerin silinmesi için kullanılan metodtur.
