**Merging a Pull Request**

​	Aynı projede çalışırken herkesin yetki seviyesi aynı olmayabilir. Herkes kendi branch'ine kodları yazıp push ederken bu branch'leri birleştirme yetkisi sadece proje yöneticisinde veya takım liderinde olabilir. Bu gibi durumlarda merge etmek yerine merge request gönderirir ve proje yetkilisi kendisi onaylarsa merge işlemi gerçekleştirilir.

​	Basit bazı durumlarda branch'lerden bir tanesinde herhangi bir değişiklik yapılmamıştır ve bu branch'in yukarıdaki bölümde belirttiğimiz ortak commit'i ve son commit'i aynıdır. Bu durumda merge işlemi çok basitleşir ve git diğer branch'in tüm commit'lerini ortak commit'in üzerine ekleyerek merge işlemini yapar. Bu özel duruma Git terminolojisinde **"Fast-Forward Merge"** denir ve her iki branch'in tarihçesi de ortaktır.

​	Fakat çoğu zaman her iki branch'de birbirinden bağımsız olarak değişikliğe uğrar ve tarihçe açısından birbirinden uzaklaşırlar. Bu durumda merge işlemini yapmak için Git'in her iki branch arasındaki değişiklikleri içeren otomatik bir commit oluşturması gerekir. Oluşturulan bu commit'e Git terminolojisinde **"Merge Commit"** denir.



**Rebase ile Değişiklikleri Entegre Etmek**

​	Bazı takımlar iki branch'i yukarıda anlattığımız otomatik merge commit'ler yerine **rebase** ile entegre etmeyi tercih edebilir. Rebase sonrasında projenizin iki farklı branch'i olduğuna dair herhangi bir tarihsel iz oluşmaz.

**$ git rebase Branch-B**

​	Bu komut ile Git öncelikle Branch-A ile Branch-B'nin ortak en son commit'ini bulup ortak commit sonrasında Branch-A'da yapılan diğer tüm commit'leri geri alır. Aslında bu commitler silinmez sadece geçici olarak farklı bir yerde saklanır. Daha sonra Branch-B'deki tüm commitler Branch-A'ya uygulanır. Son aşamada ise Branch-A'nın geçici olarak farklı bir yerde saklanan commit'leri tekrar uygulanır. Bu işlemler sonrasında tüm değişiklikler sanki sadece Branch-A üzerinde gerçekleşmiş gibi görünür.

**Squash and Merge** ile taahütleri tek bir işlemle birleştirir.

**Rebase and Merge** ile taahütleri temel dalda ayrı ayrı yeniden oluşturur.

