# Git ve Github Temelleri


## Git ve Github Temelleri

Github nedir?
 
 Projelerin depolandığı ve paylaşıldığı bir servistir. Basite indirgemek istersek yazılım için üretilmiş bir sosyal medya platformu.
 Bu platformda projelerinizi paylaşabilirsiniz. Paylaşılan projeler üzerinde geliştirmeler yapabilirsiniz. 
<!--more-->
Git nedir?
 
 Yerel projelerinizi github’a entegre etmenize ve yerel ile github arasında senkranizasyon sağlamanıza olanak veren yönetim sistemidir. 


## Kullanmaya Başlarken
> Gereklilikler
1. Github üzerinde hesap oluşturulması
2.	Blgisayarınıza git indirilip kurulması
3.	Herhangi bir proje klasörü

> Projeniz basit bir html veya txt doyası bile olabilir. Burada amaç herhangi bir klasör olmasıdır. 

## Yereldeki Projeyi Github'a Yüklemek 

1.	Github’ı hesabınıza girin ve yeni repository oluşturun. “Repositories > new” deponuzun ismini girin ve “create” butonuna tıklayın. 
![New repository](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post3/new%20repositories.png)
2.	Repositories bölümünden oluşturduğunuz depoya tıklayın. Sağ üstteki yeşil code butonuna tıklayın ve depo adresinizi kopyalayın.
![Code and Clone](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post3/clone.png)
3.	Projenizin olduğu klasörü terminalde açın. (terminalde klasörünüzün içerisine girin) 


4. {{< admonition note "Sırasıyla şu komutları girin " >}}

```
git init
git add .
gi commit –m “bir başlık yazın buraya herhangi bir şey olabilir”
git remote add origin “kopyaladığınız_url “
```
(bu adımdan sonra github hesabınız ile eşleşme yapılması istenecektir. Adımları takip ederek hesabınızı eşleştirin.)
```
git push –u origin master
```
(master kabul edilmez ise main yazarak tekrar deneyin.)
{{< /admonition >}}

Bu adımlardan sonra yereldeki proje dosyalarınız github’da açtığınız bu yeni repository’ye yüklenmiş olacaktır. Yerelde yaptığınız değişiklikleri github üzerinde güncellemek için bu komutları birincisi ve dördüncüsü hariç aynı şekilde tekrarlayabilirsiniz. 

## Github Üzerindeki Bir Projeyi Yerele Çekmek 

Github projelerini iki yöntemle bilgisayarınıza indirip kullanabilirsiniz. Burada git kullanarak nasıl yapacağınız anlatılmaktadır.
1.	Indirmek istediğiniz github projesini açın. Sağ üstteki yeşil clone butonuna tıklayın ve adresi kopyalayın. 
1.	Terminalinizi açın 
2.	Projeyi indirmek istediğiniz klasörünüze girin.
3.	{{< admonition note "Sırasıyla şu komutları girin " >}}
```
git init
git clone kopyaladığınız_url
```
{{< /admonition >}}
Proje klasörünüze indirilmiş olacaktır. 


