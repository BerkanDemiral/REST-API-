# REST-API-
# REST API KULLANIMI

Temel tanımını yapmak gerekirse; İki farklı kod parçasının birbirleri ile konuşabilmesi prensibine dayanır

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

## POSTMAN

API Testlerinde sıklıkla kullanılan bir HTTP istemcisi(client)’dir. Uygulama henüz geliştirme aşamasındayken gelecek olan verileri burada test edebiliriz. Eğer direkt url çubuğuna gerekli adresi yapıştırırsak karışık bir json formatı alırız. Burada her yapı daha düzenlidir.
