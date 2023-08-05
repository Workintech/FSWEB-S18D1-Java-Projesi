#  Java Spring REST API with JPA

### Proje Kurulumu

Projeyi öncelikle forklayın ve clone edin.
Daha sonra projeyi IntellijIDEA kullanarak açınız. README.md dosyasını dikkatli bir şekilde okuyarak istenenleri yapmaya çalışın.
Proje sayımız ilerledikçe proje yönetimimizi kolaylaştırmak adına projelerimizi belli klasör kalıplarında saklamak işimizi kolaylaştırmak adına iyi bir alışkanlıktır.
Örnek bir Lokasyon: Workintech/Sprint_1/Etud.

### Hedeflerimiz:

### Course Rest Api

 ### Başlangıç
 * Spring Initializr kullanarak bir Spring Boot projesi oluşturun.
 * İçerisinde ```Spring Web``` dependency eklenmeli.
 * Maven dependency management sistemini kullanarak tüm dependencyleri install edin.
 * Uygulamanızı  ```9000``` portundan ayağa kaldırın.
 * Bir hayvanat bahçesi için rest api dizayn etmeniz istenmektedir.

### Amaç
 * Amacımız veritabanına ekleme yapabileceğimiz bir burger API'yı hazırlamal.
 * Bu Api'yi oluştururken error handling ve validation kurallarına uymalıyız.
 * Dependency Injection kurallarına uymalıyız.
 
 ### Görev 1
 * main metodunuzun olduğu paket altında ```controller```, ```entity```, ```exceptions```, ```dao```, ```util``` isminde 5 adet daha paket oluşturunuz.
 * Project Lombok'u dependency olarak uygulamanıza ekleyin.
 * ```entity``` paketinin altına ```Burger``` adında bir sınıf tanımlayınız. İçerisinde instance variable olarak ```id, name, price, isVegan, breadType, contents``` isminde 6 tane değişken oluşturun.
 * JPA annotation larını uygulayarak bu sınıfı bir veritabanı tablosu olucak şekilde işaretleyiniz.
 * ```application.properties``` dosyanızı kullanarak veritabanı bağlantınızı kurun.
 * ```spring.jpa.hibernate.ddl-auto``` opsiyonu ile ilk başta tablonuzu create edin. Daha sonra bu opsiyonu değiştirerek tablolardaki verilerin silinmesini önleyin.
 * Spring uygulamasının veritabanı loglarını açarak veritabanına yolladığınız her soruguyu inceleyin.

### Görev 2
 * Dao paketi altında ```BurgerDao``` isminde bir interface oluşturun.
 * içerisinde şu işlemleri yapıcak methodları tanımlamalısınız.
 * ```save``` => Burger objesi alır ve bunu veritabanı tablosuna yazar.
 * ```findById``` => Integer id değeri alır ve karşılığında veritabanındaki Burger kaydını döner.
 * ```findAll``` => Hiçbir parametre almaz. Veritabanındaki bütün Burgerleri döner
 * ```findByPrice``` => price parametresi alır. Aldığı price değerinden daha büyük olan Burgerleri pricelarına göre büyükten küçüğe dogru listeler.
 * ```findByBreadType``` => BreadType parametresi alır. Bu parametreye eşit olan breadType tipindeki Burgerleri isimlerine göre alfabetik sırada küçükten büyüğe doğru sıralar
 * ```findByContent``` => Bir adet String değeri alır ve bu değeri contents tablosunda içeren tüm burgerleri döner.
 * ```update``` => Burger objesi alır ve bunu var olan burger objesi ile günceller.
 * ```remove``` => Bir adet id değeri alır ve bu id değerindeki Burger'i siler.
 * BurgerDaoImpl isimli bir sınıf yazınız. BurgerDao sınıfını ```implements``` etmeli.

 ### Görev 3
 * ```controller``` paketi altında ```BurgerController``` adında 1 tane controller yazmalısınız.
 * BurgerDaoImpl sınıfını BurgerController sınıfı altında ```Dependency Injection``` yöntemini kullanarak çağırınız
 * Amacımız CRUD işlemlerini tanımlayan endpointler yazmak.
 * [GET]/workintech/burgers => tüm burger listini dönmeli.
 * [GET]/workintech/burgers/{id} => İlgili id deki burger objesini dönmeli.
 * [POST]/workintech/burgers => Bir adet burger objesini veritabanına kaydeder.
 * [PUT]/workintech/burgers/{id} => İlgili id deki burger objesinin değerlerini yeni gelen data ile değiştirir.
 * [DELETE]/workintech/burgers/{id} => İlgili id değerindeki burger objesini veritabanından siler.
 * [GET]/workintech/burgers/findByPrice => RequestBody'de price değerini alır ve BurgerDaoImpl sınıfındaki findByPrice metodunu çağırır.
 * [GET]/workintech/burgers/findByBreadType => RequestBody'de breadType değerini alır ve BurgerDaoImpl sınıfındaki findByBreadType metodunu çağırır.
 * [GET]/workintech/burgers/findByContent => RequestBody'de content değerini alır ve BurgerDaoImpl sınıfındaki findByContent metodunu çağırır.

 ### Görev 3
 * Her endpointin hata fırlatabileceği senaryolar düşünülmeli ```exceptions``` paketi altına bu Error sınıfları oluşturulmalı.
 * Error Handling Global bir merkezden yönetilmeli. Controller sınıflarının altında olmamalı.
 * Her Controller ```@Slf4j``` ile işaretlenmelidir. Endpoint bir şekilde hata döndüğünde ```error logu``` basılmalı.
 * validation işlemleri controller sınıfı içinde kalmamalı. ```util``` paketi altında ```BurgerValidation``` isimli bir sınıf oluşturunuz. Validation işlemlerini buraya alınız.

### Görev 4
 * Codepen üzerinden veya bir React uygulaması oluşturarak Spring Boot ile yazdığımız projeye request atmayı deneyiniz.
  cors hatasını nasıl çözebiliriz.

 
