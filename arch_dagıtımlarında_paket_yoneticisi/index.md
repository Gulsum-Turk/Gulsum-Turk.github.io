# Linux Arch Dağıtımlarında Paket Yöneticisi Kullanımı


 ## Arch paket yöneticisi 
 Pacman (package manager)  archlinux ve dağıtımları için kullanılan paket yöneticisidir. Terminal kullanarak paket indirme, kaldırma, güncelleme işlemlerini yapılmasına olanak verir. 
 
 {{< admonition note "Paket İndirme" >}}
Pacman ile paket indirme komutu 

```
pacman –S paket_ismi
```
{{< /admonition >}}

>Paket ismi kurmak istediğiniz programın archlinux deposundaki ismidir. Bu depoya https://archlinux.org/packages/ adresinden ulaşabilirsiniz. 
 
![ArchRepo](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/archrepo.png)


  {{< admonition note "Paket Kaldırma" >}}
Pacman ile paket kaldırma komutu 

```
pacman –R paket_ismi
```
{{< /admonition >}}
 
  {{< admonition note "Paket Güncelleme" >}}
Pacman ile paket Güncelleme komutu 

```
pacman –Syu paket_ismi
```
{{< /admonition >}}

>> Bu komutla tüm paketlerinizi güncelleyebilirsiniz. **Paketlerinize tek tek güncelleme yapmanıza arch tabanlı dağıtımlarda destek verilmez.** Daha fazla bilgi için >> https://wiki.archlinux.org/title/System_maintenance#Upgrading_the_system


 

 
  {{< admonition note "Paket Arama" >}}
Bu komutla ismini tam olarak bilmediğiniz bir paketi depoda arayabilir ve ilgili paketleri listeleyebilirsiniz


```
pacman –Ss paket_ismi
```
{{< /admonition >}}

Paket veritabanı üzerinde sorgulama yapmak için kullanılan parametreler: –S –F –Q
Detaylı bilgi >> https://wiki.archlinux.org/title/pacman#Querying_package_databases

##  Aur (Arch User repository) Kullanımı 

Aur arch kullanıcı havuzu olarak tanımlanır. Bu havuzda kullanıcıların oluşturduğu paketler yer alır. Bu sebeple arch paket havuzundan daha fazla seçenek sunar. Örneğin zoom uygulaması aur içerisinde varken arch havuzunda yoktur. Ancak buradaki paketleri pacman komutuyla doğrudan indirmek mümkün değildir. Aur paketlerini aur yardımcı komutlarıyla veya veya pacman’e ek olarak makepkg komutuyla indirebilirsiniz. 

 yazıda pacman wrappers olarak bilinen yay ile aurdan paket indirme yöntemi anlatılacaktır. Konu hakkında daha fazla bilgi için >> https://wiki.archlinux.org/title/AUR_helpers#Pacman_wrappers


{{< admonition note "Yay Kurulumu" >}}
Yay kurulumu için sırasıyla girilmesi gereken komutlar:



```
 sudo pacman -S --needed git base-devel
 git clone https://aur.archlinux.org/yay.git
 cd yay
 makepkg -si

```
{{< /admonition >}}

Bu işlemlerden sonra yay kurulmuş olacaktır. 
### Yay ile paket indirme ve bazı komutlar: 

>> Aur paketlerini bu web sitesinden bulabilirsiniz >> https://aur.archlinux.org/packages 

* Yay –S paket_ismi >>>  aur paketini indirir ve kurar
* Yay –R paket_ismi >>> paketi siler
* Yay –Syu >> paketleri günceller
* yay --version >> versiyonunu söyler
* yay -Ss packagename  >> o isimde veya benzer aur deposunda bulunan tüm paketleri listeler
* Yay –Sc  veya yay –Scc >> yüklü paketlerin önbellekte kapladığı alanı ve gereksiz dosyalarını siler. Yani ön bellek temizliği yapar. 
* Yay –ps >> yüklü paketler hakkında bilgi verir.
------------
Detayli bilgi >> yay —help , pacman —help 




