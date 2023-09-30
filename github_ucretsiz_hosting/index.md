# Github ile Ücretsiz Hosting


## Github ile Hosting ve Subdomain Alma Rehberi

Github kullanarak ücretsiz bir web site sahibi olmak mümkün. Github pages, kullanıcılarına hosting ve subdomain hizmeti sunar. Bu yazıda sizlere github ile ücretsiz hosting ve subdomain (alt alan adı) nasıl alınır,  web site olarak nasıl kullanılır, özel domain (alan adı) github hosting servisine nasıl entegre edilir, sorularının cevabını adım adım açıklayacağım.

Öncelikle konuya yeni giriş yapanlar için hosting, domain ve subdomain kavramlarını açıklamakla başlayalım. İnternette dolaşılan her web sitesinin domain ve hostingi olmak zorundadır. Domain tarayıcınızın adres çubuğunda gördüğünüz www ile başlayan kısımdır. Örneğin şuan www.gulsumturk.com web sitesindesiniz. Yani bu web sitesinin domaini (alan adı) gulsumturk.com oluyor. 

Hosting kavramı ise ilk defa duyanlar için biraz karmaşık gelebilir. Hostingi türkçeye depolama servisi olarak çevirebiliriz. Web site sayfalarının dosyalar halinde depolandığı yerdir. Bu bilgisayarlara server denir. Bir web sitesine 7/24 ulaşılabilinmesi için bu serverlar, sürekli çalışır durumda bulunurlar. İşte bu hizmet hosting olarak adlandırılır.

Web site oluşturmak için hosting ve domain satın alabileceğiniz pek çok web sitesi bulunmaktadır. Ancak yazımızın konusu olan github Pages sayesinde bu iki hizmeti ücretsiz olarak elde etmemiz mümkün. Github kullanıcılarına, depolarını hosting olarak kullanmalarına ve githıb.io adresinde subdomain almalarına olanak tanır. Ancak burada sadece statik bir web sitesi oluştuma olanağı mevcut. Statik ve dinamik web sitesi hakkında detaylı bilgiyi [buraya]() tıklayarak ilgili yazımdan öğrenebilirsiniz. 


Şimdi github üzerinden hangi adımları gerçekleştirmemiz gerektiğine bakalım. 

### Github ile Website Oluşturma Adımları

 Github üzerinden hosting ve subdomain hizmeti alabilmek için bir adet kullanıcı hasebınızın bulunuyor olması gerekir. Github ve git kullanımının detayları için ilgili yazımızı okuyabilirsiniz. 

 1. **Github hesabınıza giriş yapın ve yeni bir depo (Repository) oluşturun.**
 ![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/depo%20new.png)

 2.	 **Deponuza kullanıcı hesabınızın ismini birebir olarak aynı vermeniz gerekiyor. İsminizden sonra “.github.io” ekleyin** 
>    Örnek > Gulsum.github.io 

![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/depo%20ismi%20.png)

Tüm işlem bu kadar. Oluşturduğunuz depo ismi web sitenizin domaini yani alan adı deponuz ise hosting görevi görür. Deponun içerisine yüklenen html, css veya javascript dosyalarıyla siteyi oluşturmaya başlayabilirsiniz. 

### Özel Alan Adını Github Hosting Servisine Entegre Etme

 Yukarıda bahsedilen şekilde alınan domain subdomaindir. Yani web sitenin adresi example.github.io şeklinde olur. Bunun yerine kendi aldığınız özel alan adını kullanmayı tercih edebilirsiniz. Sitenize özel bir alan adını kullanmak sayfanızın daha profesyonel görünmesinde etkili bir faktördür.  

 Aşağıdaki adımları takip ederek oluşturduğunuz github deponuza özel alan adını entegre edebilirsiniz. 

1.	**Deponuzu açın ve ayarlar sayfasına gidin.** 
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/ayarlar.png)
2.	**Sol tarafta bulunan menüden “Pages” a tıklayın.**
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/pages.png)
3.	**Altta bulunan Custom Domain kısmına kendi özel alan adınızı girin.**
>	Örnek > gulsumturk.com

![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/custom%20domain.png)
4.	**Learn more about configuring custum domain > Managing a custom domain for your GitHub Pages site adreslerini takip edin. Bu sayfada özel alan adınızı GitHub ile nasıl birleştireceğiniz detaylı olarak anlatılıyor.** 
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/learn.png)
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/managing.png)
5.	**Domanin alındığı web sitesine gidin ve hesabınıza girin. Aşağıdaki örnek, Google Domains üzerinden anlatılmıştır.** 
-	**Alan adınızı yönete tıklayın.**
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/y%C3%B6net.png)
-	**Sol taraftaki menüden DNS’e tıklayın.**
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/dns.png)
-	**“Özel kayıtları yönet” e tıklayın.**
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/%C3%B6zel%20kay%C4%B1tlar%C4%B1%20y%C3%B6net.png)
-	**“yeni kayıt oluştur” a tıklayın.**
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/yeni%20kay%C4%B1t%20.png)
-	**Görseldeki gibi ana makine adına “www”, tür kısmına CNAME, TTL = 600, veriler bölümüne GitHub subdomaininizi girin ve kaydete tıklayın.** 
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/cname.png)
-	**Yeni kayıt oluştura tekrar tıklayın ve bu sefer tür olarak A seçeneğini seçin. Ana makine adını boş bırakın. Veriler kısmına managing sayfasındaki apex domain başlığının altında bulunan ip adreslerini “bu kayda daha fazla ekle” butonunu kullanarak sırayla ekleyin ve kaydedin.** 
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/a%20t%C3%BCr%C3%BC.png)
![Yeni Depo Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/a%20b%C3%B6l%C3%BCm%C3%BC%20ipleri.png)
Bu işlemlerden sonra özel alan adınız ile GitHub sayfanız eşleşmiş olacaktır. 





