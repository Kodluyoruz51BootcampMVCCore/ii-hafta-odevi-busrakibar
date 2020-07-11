​																**MVC**

​	Mvc, architectural patterns'in bir parçasıdır. Model,View ve Controller kelimelerinin baş harflerinden oluşan MVC,1979 yılında Tygve Reeskaug tarafından oluşturulmuş ve yazılım geliştirmede bir çok projede kullanılmıştır. 

​	Mvc deseni 3 katmandan oluşmaktadır ve katmanları birbirinden bağımsız olarak çalışmaktadır. Bu sebeple çoğunlukla büyük çaplı projelerde projelerin yönetiminin ve kontrolünün daha rahat sağlanabilmesi için tercih edilmektedir. 

![](https://miro.medium.com/max/1400/1*1SWYJzbQSdKQbeVj4FvLwA.png)



**Model Nedir?**

​	Model,Mvc'de projenin iş mantığının oluşturulduğu bölümdür. İş mantığıyla beraber doğrulama ve veri erişim işlemleri de bu bölümde gerçekleştirilmektedir. 

​	Model tek katmandan oluşabileceği gibi kendi içinde birden fazla katmandan da oluşabilir. İç yapılandırma projenin büyüklüğü ile yazılım geliştiricinin planlamasına kalmış bir durumdur. Eğer proje büyük çaplı ise modeli birden çok katmana ayırmak projenin yönetimi açısından faydalı olacaktır.

**View Nedir?**

​	View, MVC’de projenin arayüzlerinin oluşturulduğu bölümdür. Bu bölümde projenin kullanıcılara sunulacak olan HTML dosyaları yer almaktadır. Projenin geliştirildiği yazılım dillerine göre dosya uzantıları da değişebilmektedir. Projelerin büyüklüğüne göre dikkat edilmesi gereken bir nokta ise, klasörlemedir.

​	Eğer bir web projesi geliştiriyorsanız, projenin View’larının yer aldığı klasörlerinin hiyerarşisi, ilerleyen dönemlerde karmaşıklığa sebep olmaması için dikkatli yapılmalıdır. Kimi yazılım geliştiriciler web projelerinde HTML dosyaları ile Javascript, CSS ve resim dosyalarını aynı klasör içinde barındırmaktadır. Ufak bir ayrıntı gibi görünse de projenin ilerleyen dönemlerinde ciddi problemler oluşturmaktadır.

​	View’ın bir görevi de, kullanıcılardan alınan istekleri controller’a iletmektir.

**Controller Nedir?**

​	Controller, MVC’de projenin iç süreçlerini kontrol eden bölümdür. Bu bölümde View ile Model arasındaki bağlantı kurulur. Kullanıcılardan gelen istekler Controller’larda değerlendirilir, isteğin detayına göre hangi işlemlerin yapılacağı ve kullanıcıya hangi View’ın döneceği  belirtilir.

**MVC'nin Yaşam Döngüsü**

![](https://miro.medium.com/max/1396/1*Rvnl3RndlAgUmBaEwtZ_VA.png)

**HTTP Request**

​	Sizin her ASP.NET MVC uygulamasını görüntülemek istemeniz bir request(istek) tir.Bu istediğinizi HTTP üzerinden IIS tarafından alınır. Her yaptığınız istek Server tarafından bir yanıtla
son bulması gerekir.

**Routing**

​	 ASP.NET MVC uygulamasını her istek yaptığınızda, yaptığınız yanıt UrlRoutingModule HTTP Module tarafından durdurulur. UrlRoutingModule bir isteği durdurduğu zaman, gelen istek
RouteTable’dan hangi Controller tarafından üstleneceğine karar verilir.
**Controller** 

​	RouteTable’dan gelen route bilgisine göre Controller hangi Action’ı çalıştıracaksa o View çalıştırılır. View, Controller tarafından render edilmez. Controller tarafından geriye ViewResult döndürülür.

**ViewResult** 

​	ViewResult, View’i render etmek için aktif View Engine’i çağırır.

**ViewEngine** 

​	Bir CSHTML dosyayı oluşturduğunuzda içerisindeki script ve markuplar, Razor View Engin tarafından bazı ASP.NET API’lerini sayfalarınızı HTML’e çevirmek için kullanır.

**View** 

​	View Engine tarafından HTML’e çevirilen kodlar kullanıcıya sunulur.

**Response** 

​	HTTP üzerinden View kullanıcıya gösterilir.





**MVP (Model-View-Presenter**

MVP,MVC'den evrilmiş bir paterndir. Sadece bağımlılıkları değiştirilmiş ve Controller'ın yerine Prenseter vardır.  En büyük farklı controller’ı parçalıyor olması. Böylece view/activity doğal bağına devam ederken activity, controller sorumluluklarından arınmış olur.**View’**de fark olarak bu sefer Activity ve fragment de view’dedir. Ancak herhangi bir logic implement edilmez. Burada hem view hem de presenter birer interface’i implement ediyor. Activity hem view’i hem de presenter’ı create eder.  Presenter kullanıcıdan gelen inputu view’i aracılığıyla alır.

![](https://miro.medium.com/max/672/0*mTTMpxBHlwr2JpID.jpg)

**MVVM(Model-View-ViewModel)**

​	View’in değişikliklere yanıt verebileceği event-based bir mimari kurmak istersek de karşımıza MVVM çıkacak.

​	 **Model**, MVC’yle aynı. View, viewmodelden sağlanan observable variable’ları bağlar. ViewModel, Model’i wrapleyip View tarafından ihtiyaç duyulan observable datanın sağlanmasından sorumlu.
​	Yani aslında yine business logic’den model sorumlu. Data değiştiğinde ViewModel bundan haberdar oldu ve View’e haber verdi. View’de ui’ı update etti diyebiliriz basitçe.



![](https://miro.medium.com/max/1050/0*W4ZKiiVBtfbNKja8.jpg)

**MVC-MVP-MVVM**

![](https://i.pinimg.com/originals/4c/81/29/4c8129a2ee7742652c6701fbcc6e110e.png)