---
layout: post
published: true
title: OpenShift ile Ücretsiz Java Hosting – Intellij Entegrasyonu
permalink: 2016-10-18-openshift-ile-ucretsiz-java-hosting
---
### OpenShift Nedir?

**RedHat** firmasının sunduğu bir hizmet olan **OpenShift**, üzerinde web uygulamaları barındırabileceğiniz bir bulut sistemidir. **OpenShift** üzerinde **Java, Ruby, Node.js, Python, PHP** gibi diller ile geliştirdiğiniz projeleri yayınlayabilir bunun yanı sıra **Wordpress** blogunuzu barındırabilirsiniz. Bu yazıda size **OpenShift** üzerinde bir sunucu oluşturmayı ve **Intellij** aracılığıyla kodlarımızı bu sunucu üzerinde çalıştırmayı anlatacağım.

### Gerekli Malzemeler :)

*   Intellij IDEA (Ultimate Version)
*   Git
*   OpenShift Hesabı

Hazırsanız başlayalım

### Git Kurulumu

1.  [Buraya](https://git-scm.com/downloads) tıklayarak **Git** indirme sayfasına gidelim.
2.  **Downloads** başlığı altında işletim sisteminize uygun olan versiyona tıklayalım. (Ben Windows kullanıyorum)
3.  Dosya indirme isteğine evet deyip  **Git**'i indirelim.
4.  Kurulum dosyasını açıp ayarlara dokunmadan **Next** diyerek kuralım. :)

### **OpenShift Hesabı Açma ve Application Oluşturma**

1.  [Buraya](https://openshift.redhat.com/app/account/new?then=%2Fapp%2Fconsole) tıklayarak kayıt olma sayfasına gidelim. Gerekli alanları doldurup üyeliğimizi oluşturalım.
2.  Üye olurken girdiğimiz e-posta adresine bir onay e-postası gelecektir. **Verify Your Account** yazan yere tıklayıp, açılan sayfada **I Accept** yazan butona tıklayıp üyelik işlemini tamamlayalım.
3.  Başka bir sayfaya yönlendirildik. Geldiğimiz sayfada **Create Your First Application **yazan yere tıklayalım. [![Openshift1](http://kod5.org/wp-content/uploads/2015-12-17-18_36_05-Welcome-to-OpenShift-_-OpenShift-Online-by-Red-Hat.png)](http://kod5.org/wp-content/uploads/2015-12-17-18_36_05-Welcome-to-OpenShift-_-OpenShift-Online-by-Red-Hat.png)
4.  Burada kurabileceğiniz sunucuları ve hazır paket programları(Wordpress vb.) göreceksiniz. Java başlığına ilerleyip **Tomcat 7 (JBoss EWS 2.0)** yazan yere tıklayalım. [![Openshift2](http://kod5.org/wp-content/uploads/2015-12-17-18_36_51-Create-a-New-Application-_-OpenShift-Online-by-Red-Hat.png)](http://kod5.org/wp-content/uploads/2015-12-17-18_36_51-Create-a-New-Application-_-OpenShift-Online-by-Red-Hat.png)
5.  Açılan sayfada **Public URL **başlığında iki adet girmemiz gereken alan var. 1 numaralı alana uygulamamızı ifade edecek herhangi bir isim verebiliriz. 2 numaralı alan ise bizim **OpenShift** üzerinde açtığımız uygulamaları gruplayacak olan alan. Dolayısıyla bu alana gireceğimiz isim kullanımda <span style="text-decoration: underline;">olmamalıdır</span>. [![openshift3](http://kod5.org/wp-content/uploads/2015-12-17-18_46_58-Create-a-New-Application-_-OpenShift-Onli1ne-by-Red-Hat.png)](http://kod5.org/wp-content/uploads/2015-12-17-18_46_58-Create-a-New-Application-_-OpenShift-Onli1ne-by-Red-Hat.png)
6.  **Public Url **alanını doldurduktan sonra aşağıdaki **Create Application **butonuna tıklıyoruz. [![openshift5](http://kod5.org/wp-content/uploads/2015-12-17-19_04_01-Create-a-New-Application-_-OpenShift-Online-by-Red-Hat1.png)](http://kod5.org/wp-content/uploads/2015-12-17-19_04_01-Create-a-New-Application-_-OpenShift-Online-by-Red-Hat1.png)
7.  Uygulamamız oluştuktan sonra bizi böyle bir ekran karşılayacak. Artık **Visit App In The Browser** yazan yere tıklayarak uygulamamızı görebiliriz. [![openshift6](http://kod5.org/wp-content/uploads/2015-12-17-20_08_27-Next-Steps-_-OpenShift-Online-by-Red-Hat.png)](http://kod5.org/wp-content/uploads/2015-12-17-20_08_27-Next-Steps-_-OpenShift-Online-by-Red-Hat.png)
8.  Evet, uygulamamız ayakta :) Şu anda varsayılan bir proje oluşturuldu. Bizim amacımız ise kodlarımızı bu sunucuda çalıştırmak. İşte burada IntelliJ devreye giriyor. Hazırsanız IntelliJ entegrasyonuna bakalım. ![openshift7](http://kod5.org/wp-content/uploads/2015-12-17-20_12_22-Welcome-to-OpenShift.png)

### IntelliJ Entegrasyonu

1.  **IntelliJ**'i açalım. **Configure > Settings** tıklayalım. [![2015-12-17 20_25_33-Greenshot](http://kod5.org/wp-content/uploads/2015-12-17-20_25_33-Greenshot.png)](http://kod5.org/wp-content/uploads/2015-12-17-20_25_33-Greenshot.png)
2.  **Build, Execution, Deployment** başlığı altında **Clouds**'a tıklayalım. Sağ taraftan **+** işaretine tıklayıp **OpenShift**'i seçelim. [![2015-12-17 20_30_53-Greenshot](http://kod5.org/wp-content/uploads/2015-12-17-20_30_53-Greenshot.png)](http://kod5.org/wp-content/uploads/2015-12-17-20_30_53-Greenshot.png)
3.  Açılan formda **Username** ve **Password** isimli alanlara **OpenShift** hesabımızın bilgilerini yazıyoruz ve **domain** kısmının dolması için biraz bekliyoruz. Bir süre sonra **domain** kısmına **OpenShift** üzerinde uygulama oluştururken verdiğimiz isim gelecektir. Burada en altta **Connection Successful** yazmasına da dikkat edelim. [![2015-12-17 20_35_14-Default Settings](http://kod5.org/wp-content/uploads/2015-12-17-20_35_14-Default-Settings.png)](http://kod5.org/wp-content/uploads/2015-12-17-20_35_14-Default-Settings.png)
4.  Formda görüldüğü üzere** IntelliJ**'yi **OpenShift**'e entegre etmek için yapmamız gereken tek bir şey kaldı. **SSH Key** upload etmek. **SSH**'ın ne olduğu ayrı bir yazı konusu olmakla birlikte ben sadece işimize yarayan kısmını anlatacağım.
5.  Bilgisayarımıza **Git** kurmuştuk. **Git** ile birlikte komutları yazacağımız **Git Bash** isimli konsol da yüklenmiş olmalı. **Git Bash**'i bulup açıyoruz. **SSH Key** oluşturmak için konsola "**ssh-keygen**" yazıp enter'a basıyoruz. [![2015-12-17 21_26_04-MINGW64__c_Users_HonouR](http://kod5.org/wp-content/uploads/2015-12-17-21_26_04-MINGW64__c_Users_HonouR.png)](http://kod5.org/wp-content/uploads/2015-12-17-21_26_04-MINGW64__c_Users_HonouR.png)
6.  Bize birkaç soru soracak. **SSH Key**'in adı ne olsun, şifresi ne olsun gibi. Normalde güvenlik açısından pek uygun değil fakat hepsini boş bırakıp enter'la geçebiliriz. En sonda resimdekine benzer bir şekil çıktığında **SSH Key**'imiz kırmızı çerçeve ile belirttiğim dizinde oluşmuş demektir. :) [![2015-12-17 21_30_13-MINGW64__c_Users_HonouR](http://kod5.org/wp-content/uploads/2015-12-17-21_30_13-MINGW64__c_Users_HonouR.png)](http://kod5.org/wp-content/uploads/2015-12-17-21_30_13-MINGW64__c_Users_HonouR.png)
7.  Kontrol etmek için **.ssh** klasörüne gidelim. Evet **SSH Key**'imiz burada. Şimdi 3\. adımdaki forma geri gidelim. [![2015-12-17 21_33_33-](http://kod5.org/wp-content/uploads/2015-12-17-21_33_33-.png)](http://kod5.org/wp-content/uploads/2015-12-17-21_33_33-.png)
8.  **Upload Public SSH Key** yazan yere tıklıyoruz ve az önce oluşturduğumuz **SSH Key**'imizi seçiyoruz. Burada dikkat edilmesi gereken nokta şu: **.pub** uzantılı olanı seçmeliyiz. [![2015-12-17 21_36_36-Default Settings](http://kod5.org/wp-content/uploads/2015-12-17-21_36_36-Default-Settings.png)](http://kod5.org/wp-content/uploads/2015-12-17-21_36_36-Default-Settings.png)
9.  **SSH Key**'imizin başarıyla yüklendiği mesajını aldıktan sonra **OK** deyip formu kapatıyoruz. [![2015-12-17 21_39_37-Default Settings](http://kod5.org/wp-content/uploads/2015-12-17-21_39_37-Default-Settings.png)](http://kod5.org/wp-content/uploads/2015-12-17-21_39_37-Default-Settings.png)
10.  Şimdi **OpenShift** üzerinde oluşturduğumuz uygulamayı **IntelliJ**'ye aktaralım. [Buradan](https://openshift.redhat.com/app/console/applications) oluşturduğumuz uygulamaya gidelim. [![2015-12-17 21_44_00-Applications _ OpenShift Online by Red Hat](http://kod5.org/wp-content/uploads/2015-12-17-21_44_00-Applications-_-OpenShift-Online-by-Red-Hat.png)](http://kod5.org/wp-content/uploads/2015-12-17-21_44_00-Applications-_-OpenShift-Online-by-Red-Hat.png)
11.  Uygulamanın ismine tıklayalım. Detaylar geldiğinde sağ tarafta **Source Code** başlığı altında bir kod göreceksiniz. Bu kodu kopyalayıp projeyi **IntelliJ**'ye aktarmak için kullanacağız. (Eğer kod gözükmüyorsa biraz bekleyin ve sayfayı birkaç kez yenileyin) [![2015-12-17 21_48_08-deneme _ OpenShift Online by Red Hat](http://kod5.org/wp-content/uploads/2015-12-17-21_48_08-deneme-_-OpenShift-Online-by-Red-Hat.png)](http://kod5.org/wp-content/uploads/2015-12-17-21_48_08-deneme-_-OpenShift-Online-by-Red-Hat.png)
12.  Kodu kopyaladıktan sonra, **IntelliJ**'yi açıyoruz. **Check out from Version Control** kısmından **Git**'i seçiyoruz. [![2015-12-17 21_51_19-Greenshot](http://kod5.org/wp-content/uploads/2015-12-17-21_51_19-Greenshot.png)](http://kod5.org/wp-content/uploads/2015-12-17-21_51_19-Greenshot.png)
13.  Açılan pencerede  **1** numaralı alana kopyaladığımız kodu yapıştırıyoruz. **2** numaralı alanda projenin oluşturulacağı dizini belirliyoruz. **3** numaralı alanda projenin içine koyulacağı klasörün ismini veriyoruz. **4** numaralı butona basıp kodumuzu test ediyoruz (Uyarı penceresi çıkarsa **Yes** deyin) **5** numaralı **Clone** butonuna basarak projenin indirilmesini başlatıyoruz. [![2015-12-17 21_54_09-Greenshot](http://kod5.org/wp-content/uploads/2015-12-17-21_54_09-Greenshot.png)](http://kod5.org/wp-content/uploads/2015-12-17-21_54_09-Greenshot.png)
14.  İşlem bittikten sonra bir uyarı çıkacak projeyi açmak istiyor musunuz diye. Buna **Yes** diyoruz. Karşımıza bu pencere çıkıyor. **OpenShift** projeleri varsayılan olarak **Maven** ile oluşturulur bu yüzden **Maven** olarak import ediyoruz. [![2015-12-17 22_00_46-Import Project](http://kod5.org/wp-content/uploads/2015-12-17-22_00_46-Import-Project.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_00_46-Import-Project.png)
15.  Next deyip devam edelim. [![2015-12-17 22_01_49-Import Project](http://kod5.org/wp-content/uploads/2015-12-17-22_01_49-Import-Project.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_01_49-Import-Project.png)
16.  **OpenShift** profilini seçip Next diyelim. [![2015-12-17 22_02_09-Import Project](http://kod5.org/wp-content/uploads/2015-12-17-22_02_09-Import-Project.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_02_09-Import-Project.png)
17.  Next diyelim. [![2015-12-17 22_02_37-Import Project](http://kod5.org/wp-content/uploads/2015-12-17-22_02_37-Import-Project.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_02_37-Import-Project.png)
18.  Bilgisayarımızdaki **JDK**'yı burada gösterelim. [![2015-12-17 22_03_03-Import Project](http://kod5.org/wp-content/uploads/2015-12-17-22_03_03-Import-Project.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_03_03-Import-Project.png)
19.  Kırmızı çerçeveli alana herhangi bir isim yazabilirsiniz önemli değil. **Finish** deyip bitiriyoruz. [![2015-12-17 22_03_27-Import Project](http://kod5.org/wp-content/uploads/2015-12-17-22_03_27-Import-Project.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_03_27-Import-Project.png)
20.  Projemiz geldi :) Burada gördüğünüz index.html dosyası [deneme-kod5.rhcloud.com](http://deneme-kod5.rhcloud.com/) adresine girdiğinizde gelen sayfa oluyor. [![2015-12-17 22_09_08-deneme - [C__Users_HonouR_Desktop_Kod5Deneme] - [deneme] - ..._src_main_webapp_i](http://kod5.org/wp-content/uploads/2015-12-17-22_09_08-deneme-C__Users_HonouR_Desktop_Kod5Deneme-deneme-..._src_main_webapp_i.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_09_08-deneme-C__Users_HonouR_Desktop_Kod5Deneme-deneme-..._src_main_webapp_i.png)
21.  Şimdi yaptığımız değişiklikleri gönderebilmemiz için son bir işlem daha yapıyoruz. **1** ve **2** numaralı kısımlara sırasıyla tıklayalım. [![2015-12-17 22_11_22-Greenshot](http://kod5.org/wp-content/uploads/2015-12-17-22_11_22-Greenshot.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_11_22-Greenshot.png)
22.  **1** numaralı butona tıklayıp **OpenShift Deployment**'ı seçelim. [![2015-12-17 22_12_08-Greenshot](http://kod5.org/wp-content/uploads/2015-12-17-22_12_08-Greenshot.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_12_08-Greenshot.png)
23.  Kırmızı çerçeve içindeki kısma herhangi bir şey yazabilirsiniz önemli değil. **Ok** deyip kapatalım. [![2015-12-17 22_12_57-Run_Debug Configurations](http://kod5.org/wp-content/uploads/2015-12-17-22_12_57-Run_Debug-Configurations.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_12_57-Run_Debug-Configurations.png)
24.  **index.html**'de birkaç değişiklik yapıp, değişiklikleri göndermek için **2** numaralı butona basalım. [![2015-12-17 22_15_12-Greenshot](http://kod5.org/wp-content/uploads/2015-12-17-22_15_12-Greenshot.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_15_12-Greenshot.png)
25.  Burada **1** numaralı alanda yaptığımız değişiklikler gelecek. Seçili olarak geleceği için bir şey yapmanıza gerek yok. **2** numaralı alanda göndereceğiniz kodun ne ile ilgili olduğuna dair herhangi bir şey yazabilirsiniz önemi yok. **3** numaralı butona tıklayarak tamamlıyoruz. [![2015-12-17 22_15_50-Commit and Push](http://kod5.org/wp-content/uploads/2015-12-17-22_15_50-Commit-and-Push.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_15_50-Commit-and-Push.png)
26.  Bir süre bekleyin. Kodlar **OpenShift**'e gönderilecek ve oradaki sunucu yeniden başlatılacak. İşaretlediğim şekilde **Server start** yazısını görüyorsanız artık [deneme-kod5.rhcloud.com](http://deneme-kod5.rhcloud.com) adresinden kodlarımızı test edebiliriz :) [![2015-12-17 22_21_42-deneme - [C__Users_HonouR_Desktop_Kod5Deneme] - [deneme] - ..._src_main_webapp_i](http://kod5.org/wp-content/uploads/2015-12-17-22_21_42-deneme-C__Users_HonouR_Desktop_Kod5Deneme-deneme-..._src_main_webapp_i.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_21_42-deneme-C__Users_HonouR_Desktop_Kod5Deneme-deneme-..._src_main_webapp_i.png)
27.  Veee işte sonuç :) [![2015-12-17 22_23_40-Greenshot](http://kod5.org/wp-content/uploads/2015-12-17-22_23_40-Greenshot.png)](http://kod5.org/wp-content/uploads/2015-12-17-22_23_40-Greenshot.png)

OpenShift'e deploy işlemini elimden geldiğince anlatmaya çalıştım. Umarım faydası olur.  Bu işlemler sırasında bir sorun oluşursa, bu yazının altına yorum olarak yazabilirsiniz ya da [Facebook ](https://www.facebook.com/onurozcn) üzerinden bana ulaşabilirsiniz.