# Arduino Cloud ve Wokwi ile Iot Projesi



> Bu etkinlikte wokwi similasyonu üzerinden oluşturulan projeyi Arduino Clouda bağlayacağız. Cloud üzerinden devreki ledi ve lcd ekranı kontrol edecek, dht sensöründen verileri clouda taşıyacağız. 
<!--more-->

## Adım 1: **Arduino Cloud**

1. Arduino Cloud üzerinden **ücretsiz bir hesap** oluşturun.
2. IoT projesi için yeni bir **"thing"** oluşturun.

    ![Thing Oluştur](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/Arduino/01.png)
    ![Thing Oluştur](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/Arduino/02.png)



Bu sayfada üç bölüm var. "Variables" bizim projemizde kullancağımız değişkenleri ifade eder. "Device" kısmından kullanılacak cihaz tanımlaması ve yönetimi yapılır. "Network" kısmından ağ ayarları gerçekleşir. 
![Network Ayarları](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/Arduino/03.png)

3. Proje için dört adet variable oluşturun:

    1. **İsim:** sicaklik, **Tür:** Temperature sensor (°C), **İzinler:** *Read Only*
    2. **İsim:** nem, **Tür:** Relative humidity, **İzinler:** *Read Only*
    3. **İsim:** mesaj, **Tür:** Character string, **İzinler:** *Read & Write*
    4. **İsim:** led, **Tür:** Boolean, **İzinler:** *Read & Write*

    ![Variable Oluşturma](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/Arduino/04.png)

4. Ardından, **"device"** ayarlamalarına geçin ve şu adımları takip ederek cihazı seçin:

    - Add device > Third party device > ESP32 > DOIT ESP32 DEVKIT V1

 > Bu adımları tamamladıktan sonra **"secret key"** ve **"device id"** bilgilerini kopyalayın ve not defterine kaydedin!

   

5. Son olarak, **network ayarlarını** yapılandırın. Wi-fi name olarak **"Wokwi-GUEST"** yazın ve password kısmını boş bırakın. Secret key kutucuğuna kopyaladığınız secret key'i ekleyin.

    

## Adım 2: **Arduino Cloud Dashboard**

1. Sol menüden **Dashboard'ı** seçin.
2. **"CREATE DASHBOARD"** butonuna tıklayarak yeni bir dashboard oluşturun.
3. Düzenleme bölümüne geçin ve Add butonuna tıklayarak şu adımları takip edin: 
    
    
    Things > proje_ismi > Tüm variable'ları seçin > **"Create widgets"** diyerek tamamlayın.

    ![Dashboard Ayarları](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/Arduino/05.png)
    ![Dashboard Ayarları](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/Arduino/06.png)

## Adım 3: **Wokwi Simülasyonu**

Bu projenin Wokwi uygulamasının [hazır linkine buradan ulaşabilirsiniz](https://wokwi.com/projects/383461584635405313).

Kodları kendi cloudunuza göre düzenlemek için `thingsProperties.h` dosyasını açın ve aşağıdaki kısımları kendinize göre değiştirin.

- DEVICE_LOGIN_NAME "kaydettiğiniz_device_id"
- DEVICE_KEY "kaydettiğiniz_secret_key"

![Wokwi](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/Arduino/07.png)



## Adım 4: **Projeyi Çalıştırma**

Artık simülasyonu başlatabilirsiniz. Simülasyonun clouda bağlanması birkaç dakika sürebilir. Simülasyon önce wi-fi ye bağlanacak ardından cloud ile bağlantı kuracaktır. 

Dashboardda oluşturduğunuz widgetlardan simülasyondaki ledi ve lcd yi kontrol edebilir, dht sensörden gelen verileri de ilgili widgetlarda görebilirsiniz. 





