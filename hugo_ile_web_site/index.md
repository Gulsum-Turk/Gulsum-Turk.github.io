# Hugo ile Website Yapımı

## Hugo
Hugo nedir: Hugo, Go dili ile yazılmış ve web sitesi oluşturmayı yeniden eğlenceli hale getirmek için tasarlanmış hızlı ve modern bir statik site oluşturucudur.
<!--more-->

Gereklilikler: 
1. [Hugo](https://gohugo.io/installation/)'nun indiirlmesi
2. [Git](https://gohugo.io/installation/)'in indiirlmesi

### Windows için hugo indirme 
Chocolatey, Scoop veya Winget paket yöneticilerinden herhangi biri ile indiribeilirsiniz.

komutlar:

```
choco install hugo-extended
scoop install hugo-extended
winget install Hugo.Hugo.Extended
```

### Linux için hugo indirme

{{< admonition note "Paket yöneticisine göre indirme komutları" >}}
1. Snap ile indirme:

```Sudo snap install hugo```

2. Homebrew ile indirme:

```Brew install hugo```

3. ArchLinux dağıtımları için indirme:

```Sudo pacman –S hugo```

4. Dabian dağıtımları için indirme:

```Sudo apt install hugo```

5. Fedora için indirme:

```Sudo dnf install hugo```


{{< /admonition >}}


## Başlangıç
Web sitesini oluşturmaya başlamadan önce siteniz için bir tema seçmelisniz. Hugo web sitesinde seçebileceğiniz farklı tema tasarımları bulunur. [Buradan](https://themes.gohugo.io/) temalara ulaşabilirsiniz. 

#### Yeni bir web sitesi oluşturma adımları

Terminalinizi açın ve site klasörünüzü oluşturmak istediğiniz dizine gidin. Bundan sonra yapılması gereken aşağıdaki komutları sırasıyla girmek.

{{< admonition note "Site Oluşturma" >}}

```hugo new site Site_ismi```

Site_ismi adında bir klasör oluşturarak projeye gerekli altyapıyı kurar.

```cd Site_ismi```

Klasörün içerisine girer.

```git init```

Klasörü git ile ilişkilendirir.

```git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke```

Siteniz için seçtiğiniz temayı ekler. Burada örnek olarak ananke teması verilmiştir. Kırmızı ile belirtilen yere kendi temanızın github adresini ekeyin. Github temelleri için [tıklayınız](https://gulsumturk.com/git_github_temelleri/).

```echo "theme = 'ananke'" >> hugo.toml```

Hugo.toml dosyası sitenizin yapılandırma ayarlarının buunduğu dosyadır. Bu komutla temanızı bu dosyaya kaydetmiş olacaksınız. 

```hugo server```

Hugo server komutu sitenizi görüntelemenize olanak sağlar. Görselde belirtilen linke tıklayarak sitenizin görünümünü inceleyebilirsiniz. 
{{< /admonition >}}
![server](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post4/server.png)
## İçerik Eklenmesi
Content klasörünüz içeriklerinizin yer alacağı klasördür. Projenizin olduğu klasör içerisinde aşağıdaki komutla yeni bir post oluşturabilirsiniz. 

```hugo new content posts/my-first-post.md```

![draft bölümü](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post4/draft.png)

Draft bölümün true olması içeriğin taslak olaak kaydedildiği ve görünmeyeceği anlamına gelir. İçeriği yayınlamak için draft’ı false yapın.  İçerik kısmını markdown ile kolayca oluşturabilirsiniz. Markdown yazımı temelleri için [tıklayınız](https://gulsumturk.com/iki/).

## Ayarlar ve Yayınlama
Projenizdeki hugo.toml dosyasının yapılandırma ayarlarını barındırdığını söylemiştik.  Buradaki ayarları inceliyerek siteniz için gerekli olanları yapılandırabilirsiniz. 
![Config](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/post4/config.png)

1. Base url: burada example.org kısmını silerek sitenizin url sini ekleyin. 
2. Dil kısmına Temanızdaki dil bölümünden dil kodunuzu yapıştırın. Türkçe için >>
3. Title= site başlığı

#### Yayınlama:
Hugo komutu : Bu komutu kök dizinde çalıştırdığınızda hugo public adında bir klasör oluşturur. Bu klasör mevcut sitenizin yayınlanmaya hazır html dosyalarıdır. Public Klasörünü yayınlayabilirsiniz. 

```hugo```
