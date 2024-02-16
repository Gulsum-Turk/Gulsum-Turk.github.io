# Arduino Trafik Seti Projesi



**Arduino ile Kırmızı Işıkta Duran araba Yapmak**

Arduino trafik projesi, uzaktan kumandalı araba ve trafik setini içerien bir *IOT projesidir.* Bu projede **esp8266 kartı** ile wifi üzerinden kontrol edilebilen bir araç geliştirilmiştir. Trafik setinde ise arduino kartı ile trafik ışıklarının kırmızı ve yeşil olarak yanmasını sağlıyoruz. Projedeki kodlar aracın önüne bariyer çıktığında ilerlemesini engelleyecek şekilde ayarlanmıştır. 
<!--more-->


![](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/arduino_araba/proje.png)

## Arabanın Geliştirilmesi
![](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/arduino_araba/araba.png)
Malzemeler;
Araç için hazır satılan arduino araç setlerini alabilirsiniz. Bunlardan hariç **mesafe sensörü** ve wifi bağlantısı için **esp8266 NodeMCU** karta ihtiyacınız olacak.
1. Araç parçaları: Tekerlekler ve gövdesi 
2. 2 adet DC Motor
3. L298N Motor sürücüsü
4. HC-SR04 Ultrasonik mesafe sensörü
5. NodeMCU Esp8266 Kart

 **Araç Malzemeleri**
![Araç malzemeleri](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/arduino_araba/malzemeler.png)
 **Motor Sürücü**
![L298N Motor sürücüsü](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/arduino_araba/dcmotorsurucu.png)


### 1. Adım: Arabanın monte edilmesi

Aşağıdaki devre şemasına göre arabanın montajını yapabilirsniz. 
![Devre Şeması](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/arduino_araba/arabadevre.png)
Detaylı montaj için videoyu izleyin.
[Araba Montaj Videosu](https://www.youtube.com/watch?v=huWn4Sx99hQ)


### 2. Adım: Apk nın yüklenmesi

Arabayı wifi üzerinden  kontrol edeceğimiz apkyı indiriyoruz. Aşağıda verilecek hazır kod ile nodemcu nun kendi wifisinin oluşturulması sağlandı. İndirilen apk ile Nodemcunun yani arabanın wifisine bağlanıp kontrol sağlanacaktır. Apk indirme linki: [Apk Linki](https://drive.google.com/file/d/1vfaSqICAD94_eSD9ypOP2p_UH5IIEA4C/view)

### 3. Adım: Kodlama
Aşağıdaki kodu esp kartınıza yükleyiniz. Esp kartınıza ilk defa yükleme yapıyorsanız Arduino ide üzerinizden öncelikle kartınızı seçmiş olmanız gerekir.

``` 
// Motor kontrol pinleri
#define ENA 14 // Sağ motorların hızını kontrol etmek için kullanılan pin (Enable) GPIO14(D5)
#define ENB 12 // Sol motorların hızını kontrol etmek için kullanılan pin (Enable) GPIO12(D6)
#define IN_1 15 // Sağ motorun ileri yönde dönüşünü kontrol etmek için kullanılan pin GPIO15(D8)
#define IN_2 13 // Sağ motorun geri yönde dönüşünü kontrol etmek için kullanılan pin GPIO13(D7)
#define IN_3 2 // Sol motorun ileri yönde dönüşünü kontrol etmek için kullanılan pin GPIO2(D4)
#define IN_4 0 // Sol motorun geri yönde dönüşünü kontrol etmek için kullanılan pin GPIO0(D3)
// Kütüphaneler
#include <ESP8266WiFi.h>
#include <WiFiClient.h>
#include <ESP8266WebServer.h>
// Uygulama komut durumu ve motor hızı değişkenleri
String command; // Uygulama komut durumunu saklamak için kullanılan String.
int speedCar = 800; // Motor hızı (400 - 1023).
int speed_Coeff = 3; // Motor hızı katsayısı.
// Mesafe sensörü pinleri
int trigPin = 4;
int echoPin = 5;
// Mesafe ölçümü için değişkenler
long zaman;
long mesafe;
// WiFi ayarları
const char* ssid = "NodeMCU Car";
ESP8266WebServer server(80);
void setup() {
 // Mesafe sensörleri için pin modları ayarlanıyor
 pinMode(trigPin, OUTPUT);
 pinMode(echoPin, INPUT);
 // Motor pinlerinin modları ayarlanıyor
 pinMode(ENA, OUTPUT);
 pinMode(ENB, OUTPUT);
 pinMode(IN_1, OUTPUT);
 pinMode(IN_2, OUTPUT);
 pinMode(IN_3, OUTPUT);
 pinMode(IN_4, OUTPUT);

 Serial.begin(115200);

 // WiFi bağlantısı yapılıyor
 WiFi.mode(WIFI_AP);
 WiFi.softAP(ssid);
 IPAddress myIP = WiFi.softAPIP();
 Serial.print("AP IP address: ");
 Serial.println(myIP);
 // Web sunucusu başlatılıyor
 server.on("/", HTTP_handleRoot);
 server.onNotFound(HTTP_handleRoot);
 server.begin();
}
void goAhead() {
 // İleri git fonksiyonu
 digitalWrite(IN_1, LOW);
 digitalWrite(IN_2, HIGH);
 analogWrite(ENA, speedCar);
 digitalWrite(IN_3, LOW);
 digitalWrite(IN_4, HIGH);
 analogWrite(ENB, speedCar);
}
void goBack() {
 // Geri git fonksiyonu
 digitalWrite(IN_1, HIGH);
 digitalWrite(IN_2, LOW);
 analogWrite(ENA, speedCar);
 digitalWrite(IN_3, HIGH);
 digitalWrite(IN_4, LOW);
 analogWrite(ENB, speedCar);
}
void goRight() {
 // Sağa git fonksiyonu
 digitalWrite(IN_1, HIGH);
 digitalWrite(IN_2, LOW);
 analogWrite(ENA, speedCar);
 digitalWrite(IN_3, LOW);
 digitalWrite(IN_4, HIGH);
 analogWrite(ENB, speedCar);
}
void goLeft() {
 // Sola git fonksiyonu
 digitalWrite(IN_1, LOW);
 digitalWrite(IN_2, HIGH);
 analogWrite(ENA, speedCar);
 digitalWrite(IN_3, HIGH);
 digitalWrite(IN_4, LOW);
 analogWrite(ENB, speedCar);
}
void goAheadRight() {
 // Sağa çapraz ileri git fonksiyonu
 digitalWrite(IN_1, LOW);
 digitalWrite(IN_2, HIGH);
 analogWrite(ENA, speedCar/speed_Coeff);
 digitalWrite(IN_3, LOW);
 digitalWrite(IN_4, HIGH);
 analogWrite(ENB, speedCar);
}
void goAheadLeft() {
 // Sola çapraz ileri git fonksiyonu
 digitalWrite(IN_1, LOW);
 digitalWrite(IN_2, HIGH);
 analogWrite(ENA, speedCar);
 digitalWrite(IN_3, LOW);
 digitalWrite(IN_4, HIGH);
 analogWrite(ENB, speedCar/speed_Coeff);
}
void goBackRight() {
 // Sağa çapraz geri git fonksiyonu
 digitalWrite(IN_1, HIGH);
 digitalWrite(IN_2, LOW);
 analogWrite(ENA, speedCar/speed_Coeff);
 digitalWrite(IN_3, HIGH);
 digitalWrite(IN_4, LOW);
 analogWrite(ENB, speedCar);
}
void goBackLeft() {
 // Sola çapraz geri git fonksiyonu
 digitalWrite(IN_1, HIGH);
 digitalWrite(IN_2, LOW);
 analogWrite(ENA, speedCar);
 digitalWrite(IN_3, HIGH);
 digitalWrite(IN_4, LOW);
 analogWrite(ENB, speedCar/speed_Coeff);
}
void stopRobot() {
 // Robotu durdur fonksiyonu
 digitalWrite(IN_1, LOW);
 digitalWrite(IN_2, LOW);
 analogWrite(ENA, speedCar);
 digitalWrite(IN_3, LOW);
 digitalWrite(IN_4, LOW);
 analogWrite(ENB, speedCar);
}
void loop() {
 // Web sunucusu istekleri kontrol ediliyor
 server.handleClient();
 // Mesafe ölçümü yapılıyor
 digitalWrite(trigPin, LOW);
 delayMicroseconds(5);
 digitalWrite(trigPin, HIGH);
 delayMicroseconds(10);
 digitalWrite(trigPin, LOW);
 zaman = pulseIn(echoPin, HIGH);
 mesafe = (zaman / 29.1) / 2;

 // Mesafe kontrolü yapılıyor
 if (mesafe < 15) {
 stopRobot();
 } else {
 // Uygulama komut durumu kontrol ediliyor
 command = server.arg("State");
 if (command == "F") goAhead();
 else if (command == "B") goBack();
 else if (command == "L") goLeft();
 else if (command == "R") goRight();
 else if (command == "I") goAheadRight();
 else if (command == "G") goAheadLeft();
 else if (command == "J") goBackRight();
 else if (command == "H") goBackLeft();
 else if (command == "0") speedCar = 400;
 else if (command == "1") speedCar = 470;
 else if (command == "2") speedCar = 540;
 else if (command == "3") speedCar = 610;
 else if (command == "4") speedCar = 680;
 else if (command == "5") speedCar = 750;
 else if (command == "6") speedCar = 820;
 else if (command == "7") speedCar = 890;
 else if (command == "8") speedCar = 960;
 else if (command == "9") speedCar = 1023;
 else if (command == "S") stopRobot();
 }
}
void HTTP_handleRoot(void) {
 // Web sunucusu kök dizini işleniyor
 if (server.hasArg("State")) {
 Serial.println(server.arg("State"));
 }
 server.send(200, "text/html", "");
 delay(1);
}

```


## Trafik Setinin Geliştirilmesi
![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiwSj73uj0iVACQys1LxHe3jJQYyOokEXCgIsEzWR1aN0lPJ3SeN2kcUl1sT5knmRAHbmQ0vLvnDdl0qgr6suD37MwvHdQZTRiCiTct2GCFSVuzimYY67s_e1mp_GWCk_8OfeuEJmmjJMW-/s2048/IMG_20210312_164629.jpg)
Trafik setinde arabanın ve yayanın geçeceği iki adet yol tasarlandı. Yayalara kırmızı yandığında araçlara yeşil yanmaktadır. Aynı zamanda kırmızı yanan tarafın geçişini engellemek için yol girişleri kırmızı ışıkta bariyer ile kapatılır.

Malzemeler

1. Karton malzemeler (yolların ve ışık direklerinin yapılması için)
2. Bariyerler için iki adet micro servo motor
3. Arduino uno
4. Trafik ışıkları için ledler



### Adım 1: Fiziksel bağlantıların yapılması 

Trafik setinin tasarımını yaptıktan sonra bağlatıları aşağıdaki gibi yapın. Servo motorların hareket eden koluna yolu kapatıp açacak bariyerleri bağlayın.
![Devre Şeması](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/arduino_araba/setdevre.png)

![Servo motor pinleri](https://raw.githubusercontent.com/Gulsum-Turk/pictures/main/arduino_araba/servo.png)
### Adım 2: Kodlamanın yapılması 
Adruino uno ya yüklenecek gerekli kodlar aşağıdadır.
``` 
#include <Servo.h> //import library

Servo myservo; 

int led = 13
Servo myservo1;   

int led1 = 12; 

void setup() 

{ 

  pinMode(led, OUTPUT); 

   myservo.attach(9, 500, 2500);   

  pinMode(led1, OUTPUT);

  myservo1.attach(10, 500, 2500);

} 

void loop() 
{ 
    // Rotate Servo 3 by 180 degree



  myservo.write(90);

  myservo1.write(0);

  delay(10); 



 digitalWrite(led, HIGH);   

  delay(8000);              

  digitalWrite(led, LOW);  

  

  myservo.write(0);

  myservo1.write(0);

  delay(1000); 



  myservo.write(0);

  myservo1.write(90);

  delay(10); 



   digitalWrite(led1, HIGH);   

  delay(8000);               

  digitalWrite(led1, LOW);    



  myservo.write(0);

  myservo1.write(0);

  delay(1000); 
}
```
