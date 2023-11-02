# Node.js Kurulumu: Linux arch tabanlı dağıtımlar




Arch tabanlı Linux işletim sistemlerine Node.js kurmak için birkaç farklı yöntem vardır. En yaygın yöntemlerden biri, Node.js'yi paket yöneticisi aracılığıyla kurmaktır.
<!--more-->
###  Kurulum
> pacman ile kurulum
```
pacman -S nodejs
```
Bu komut, Node.js'nin en son kararlı sürümünü kuracaktır.
> Aur ile kurulum

Arch User Repository (AUR), Arch tabanlı Linux dağıtımları için üçüncü taraf paketlerin bir havuzudur. AUR'dan Node.js'yi kurmak için aşağıdaki komutu kullanın:
```
yay -S node
```
**2. Node.js Kurulumunu Doğrulama**

Node.js'nin başarıyla kurulduğunu doğrulamak için aşağıdaki komutlardan birini kullanın:
```
node
node -v
node --version
```
Bu komutlar, Node.js'nin kurulu sürümünü görüntüleyecektir.

### npm

npm, Node.js için bir paket yöneticisidir. Node.js uygulamaları için gerekli olan modülleri ve paketleri bulmak, yüklemek, güncellemek ve kaldırmak için kullanılır.
npm, JavaScript tabanlı uygulamalar geliştirmek için yaygın olarak kullanılan bir araçtır. Node.js'nin varsayılan paket yöneticisidir ve dünyanın en büyük yazılım kayıt defterlerinden biridir.

npm, aşağıdakiler için kullanılabilir:

- Node.js uygulamaları için gerekli olan modülleri ve paketleri bulmak ve yüklemek
- Modülleri ve paketleri güncellemek ve kaldırmak
- Modüllerin ve paketlerin bağımlılıklarını yönetmek
- Modülleri ve paketleri paylaşmak ve dağıtmak

**1. npm kurulumu**
> Eğer node.js'i pacman ile kurduysanız aşağıdaki komutu terminalde çalıştırarark npm'i kurabilirsiniz.
```
npm install -g npm
```
> Kurulumu yay ile yaptıysanız aşağıdaki komutu giriniz.

```
yay -S npm
```

Bu komutlar, npm'nin en son kararlı sürümünü kuracaktır.

**2. npm Kurulumunu Doğrulama**

```
npm -v
npm --version
```
