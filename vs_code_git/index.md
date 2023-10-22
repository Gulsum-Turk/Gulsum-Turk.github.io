# Vs Code ile Git Kullanımı


## VS Code Git: Terminalsiz Git Kullanımı 

Git işlemlerinin tamamı terminal kullanmadan vs code üzerinden nasıl yapılır, bu yazıda anlatılmaktadır. 

### Git ile ilişikilendirme
Terminalde "git init" olarak verdiğimiz bu komutu Vs Code'da basit şekilde yapmak mümkün. Sol taraftaki icon bardan üçüncü ikon Vs Code'da git işlemelerini yapmaya ve takip etmeye olanak sağlar. 
<!--more-->
![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/1.png)
    Bu ikon tıklandığında aşağıdaki gibi bir görüntü gelecektir. Kırmızı alan içerisinde belirtilen “Initialize Repository” Vs Code'da açmış olduğunuz klasörü git ile ilişkilendirir. Bu işlemden sonra açılan sıdebarda commit, remote, push gibi diğer işlemleri yapmak mümkün.
    ![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/2.png)

![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/3.png)
    Source Control Repositories başlığı altında git ile ilişkilendirilen klasörleriniz yer alır. Source Control bölümü altında yapılan değişiklikler gösterilir. 

![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/4.png)
### Commit
Yukarıdaki görselde git_ornek klasörü git ile ilişkilendirilmiş ve içerisine iki adet dosya eklenmiştir. Şimdi bu değişiklikleri commit edelim. "Message" kutusuna commit mesajınızı yazdıktan sonra butona tıklıyoruz. 

![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/5.png)
    **Mesaj olarak “files added” yazıp commit butonuna tıklıyorum. Commit işlemi tamamlandı.**
### Git History
Git history, Vs Code'da git geçmişini görüntülemenizi sağlayan bir eklentidir. Aynı zamanda bu eklentiden yaptığız işlemleri geri almanız da mümkündür. Eklentiyi kurmak için Vs Code eklentiler bölümünden "git history" şeklinde aratıp kurunuz. 

![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/6.png)
![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/7.png)
    
Eklentiyi kurduktan sonra klasörün kenarına görselde belirtilen saat ikonu gelecektir. Bu ikona tıklandığında o klasörde yapılan tüm işlemleri görmek mümkün. Yukarıda yaptığımız commiti şimdi Git History’den inceleyelim. 

![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/8.png)
Git history sayfası ikiye bölünmüştür. Üst kısımda yapılan commit işlemleri görünür. Biz bu klasör için henüz bir adet commit yaptığımız için br commitimiz listelendi. Alt kısımda ise seçili commitin ayrıntıları yer alır. Bu ekrandaki mavi butonlardan birkaçının ne işe yaradığına bakalım: 
1. Soft ve hard: Bu iki işlem yaptığımı commiti siler.  
2. Workspace: Dosyanın anlık durumu ile commit edilen halini karşılaştırır.
3. Previous: Dosyanın bir önceki commiti ile seçili commitini karşılaştırır. 

Bu karşılaştırmalarda yapılan değişiklikler silinenler kırmızı, eklenenler yeşil olarak gösterilir. 
Şimdi klasöre örnek olması için yeni bir dosya ekliyorum ve tekrar commit ediyorum. 

![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/9.png)
**Yukarıdaki gibi newfile.txt dosyasını ekledim ve “add new files” mesajıyla commit işlemni gerçekleştirdim.** 

![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/10.png)
**İkinci commitim history sayfamda listeye eklenmiş durumda.** 
### Githuba yükleme: Push ve remote
commit yaptıktan sonra seçili klasör için source Control başlığı altında “Publish Branch” butonu oluşacaktır. Bu butona tıklandığında github üzerinde oluşturulacak deponun private yada public mi olması gerektiğini soracaktır. Biz public olanı seçip devam ettiğimizde yeni depo oluşturma, remote ve push olmak üzere bu üç işlemin tamamı otomatik olarak gerçekleştirilir.  

**Publish Branch > Public** 

![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/11.png)
**Github üzerinde oluşan yeni depo:**

![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/12.png)
### Diğer işlemler: Pull, clone, fetch, branch vs. 
**Klasörün yanındaki üç noktadan diğer işlemlere ulaşabilirsiniz.** 

![Server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post5/13.png)
