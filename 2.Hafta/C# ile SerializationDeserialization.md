​										**C# ile Serialization/Deserialization**

​	Veri merkezli uygulamalarda verileri saklamak veya transfer etmek gibi durumlarla sık sık karşılaşırız. Verilerin bir kaynaktan alınması veya bir yere depolanması nesneler aracılığı ile gerçekleştirilir. Ancak her programlama dilinde farklı yani platformda kendine özgü bir nesne yapısı olduğundan dolayı,bir platformun diğerinin nesne yapısını bilmesi beklenemez. 

​	Bu gibi durumlarda verilerin platform bağımsız bir şekilde depolanması veya transfer edilmesi amacıyla bazı standartlar oluşturulmuştur. Bu standartlardan bazıları Binary,Simple Object Access Protocol,Json veya Xml şeklinde belirlenmiştir.



**Serialization Nedir?**

Bir nesnedeki verinin bir yerde depolanması veya ağ ortamında bir yerden bir yere gönderilmesi gerektiği durumlarda uygun formata dönüştürülmesi işlemidir.

![](http://www.bayramucuncu.com/wp-content/uploads/2011/12/serialization.gif)

**.Net Framework ile Serialization**

​	Serileştirme işlemini ve serileştirilmiş nesneleri dönüştürme işlemini gerçekleştirecek olan nesneler, *System.Net.Runtime.Serialization* ad uzayında bulunmaktadır.

 **Serialization** işlemi, bir nesneyi, depolamak veya serileştirmek amacıyla istenen formata dönüştürme işlemidir.

 **Deserialization** ise serileştirilmiş biçimdeki verilerin tekrar nesnelere dönüştürülmesi işlemidir. 

Örneğin, network ortamında bir bilgisayardan başka bir bilgisayara veri transferi gerçekleştirmek için önce bağlantı kurulur, ardından gönderilecek olan nesne oluşturduğumuz uygulama tarafından serileştirilir, daha sonra uzak bilgisayardaki uygulama tarafından deserialization işlemi ile aktarılan veri anlamlı bir nesneye dönüştürülür.



**JSON Serialization**

Nesneleri JSON şeklinde serinleştirme işlemi için Json.Net kütüphanesi kullanılabilir. 



**Örnek Olarak JSON serialization nesne**

`public static string JsonSerialize(object graph){`

​	return JsonConvert.SerializeObject(graph);

`}`

public static object JsonDeserialize (string seralized){

​	return JsonConvert.DeserializeObject(seralized);

}

![](https://www.bayramucuncu.com/wp-content/uploads/2011/12/json.png)

Json serileştirme sonucunda .Net ile ilgili bilgiler JSON nesnesine eklenmez.  

Örneğin nesnenin hangi namespace ve hangi sınıfa ait olduğu bilgisi yoktur. Bu bilgilerin eklenmesini istiyorsanız **jsonSerializerSettings** sınıfını serileştirme ve deserileştirme işlemi sırasında kullanmalısınız. 