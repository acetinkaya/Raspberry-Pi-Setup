# Raspberry-Pi-Setup

https://www.raspberrypi.com/products/raspberry-pi-4-model-b/ cihazı üzerinde;

---Elimizdeki cihaz hakkında---

4GB RAM,

2.4GHZ ve 5GHZ destekleyen IEEE 802.11ac WiFi ve Bluetooth 5.0 modülü,

Gigabit Ethernet Portu,

2 Adet Usb 3.0 Girişi,

2 Adet Usb 2.0 Girişi,

2 Adet Micro HDMI Portu,

Micro-SD Kart Yuvası ve Standart 40 Pin Yapısı bulunmaktadır. Ayrıca bu cihazın güç kontrolü için USB-C Tipi Güç Girişinden 5v 3A besleme gerekmektedir.

---Kurulum Adımları---

Kurulum İşlemleri İçin Gerekenler;

•	SD Kart Fomatter Yazılımı (Kurulum yapılacak SD kartın fortmanlana bilmesi için kullanılacaktır)

•	https://www.raspberrypi.com/software/operating-systems/ linki üzerinden; Raspberry Pi tavsiye edilen kurulum (recommended software) dosyasını indiriyoruz. İndirilecek *.iso dosyasını bilgisayarda bir konuma kayıt edin. Örneğin masaüstüne.

•	Win32 Disk Manager yazılımı ile formatlanan SD karta *.iso dosyasını yazdırıyoruz. Ortalama 10-15 dakikalık kurulumdan sonra SD kartı Raspberry’e takıp çalıştırıyoruz. 

---Kurulum İşlemleri Tamamlandı---

Kurulum işlemleri tamamlandıktan sonra ayarlar ve yapılandırma işlemleri gerekmektedir. Bu işlemler sırası ile;

--- Ayarlar ---

Menü’den >>> Preferences >>> “Rasberry Pi Configuration” bölümünü açıyoruz. 

•	Raspberry üzerinde ayarlar ve yapılandırmalar açılan menü/pencere üzerinde olacaktır.

•	İlgili Menunun detaylı anlatım ve görsel içerikleri bu link üzerindedir https://www.raspberrypi.com/documentation/computers/configuration.html 

•	Raspberry üzerinde açılan menü “Raspberry Pi Configuration” Raspberry donanımı üzerinde açılıp kapanmasını istediğiniz portlar, görüntü ayarları, arayüz ayarları, şifre işlemleri, donanım performans ayarları, konum işlemlerine bağlı olarak saat ve gün ve wifi ayarlarını yapılabilmektedir. İlgili menülerin aktif veya pasif yaptıktan sonra donanım resetlenmek isteyecektir. Onayınız sonrası sistem yeniden başlatılacaktır. 

DİP NOT: Açıp kapattığınız ayarları bir noktalara kaydetmenizi tavsiye ederim. Raspberry üzerinde oluşabilecek hatalar anında hangi ayarı açıp-kapattığınızı bilmelisiniz. Hangi sensörün portunu ilgili projenizde kullanacaksanız o zaman aktif veya pasif yapın!!!!!! Ayrıca kapatıp açtığınız port ve ayarlar sistemin kilitlenmesine neden olabilir. O zaman SDkarta yeniden kurulum yapmanız gerekmektedir. Bu konuda internette araştırma yaparak daha net sonuçlara erişebiliriz. Tek bir blog sayfasını ele alarak işlem yapmayın!!!!!!

--- Ayarlar Tamamlandı ---

Raspberry Pi’yi kendi donanımına bağlı klavye,mause ve monitör ile veya uzaktaki bir cihazdan yönetmenize imkan tanımaktadır. Uzaktan bağlanma durumunda “Raspberry Pi Configuration”  bölümünden SSH ve VNC etkinleştirmesi gerekmektedir. 

“Raspberry Pi Configuration”  >>> Interfaces >>> SSH >>> Enable seçerek uzaktan erişimi aktif hale getiriyoruz. 

•	Komut satırından sudo raspi-config >>> 3 Interfacing Options >>> I2 SSH >>> ENABLED >>> YES işlem adımları ile SSH’ı aktif hale getirebilmekteyiz. 

•	sudo systemctl status ssh >>> yazıldığında “active (running)” ifadesinin görülmesi gerekmektedir.  

•	VNC arayüzünü bağlantı kurmak için kullanacağız. “Raspberry Pi Configuration”  >>> Interfaces >>> VNC >>> Enable seçerek erişimi aktif hale getiriyoruz.

•	Komut satırından sudo raspi-config >>> 5 Interfacing Options >>> I3 VNC >>> ENABLED >>> YES işlem adımları ile VNC’yi aktif hale getirebilmekteyiz. 

Bu işlemler ile Raspberry yanınızda olmadığında modemden Raspberry’e port açıp uzaktan bağlantı sağlayabiliyoruz.

---- Raspberry Üzerinde Saat ve Tarih Ayarlama ---

sudo date -s "18 APR 2022 14:45"

•	Tarih ve saat ayarlamanız sistem üzerinde yapacağınız işlemlerde size kolaylık sağlayacaktır. Kurulumlarda hata almamanız için bu işlem adımı önemlidir.

--- Saat ve Tarih Ayarlaması Tamamlandı ---

--- Terminal Ekranının Kullanımı ---

Bu bölüm içerisinde Raspberry Pi’nin komut düzeyinde kullanımı belirtilmiştir. Komutlar üzerinden yapılacak işlemler farklı amaçlar için kullanılacaktır. Bunlardan bazıları işlevleriyle birlikte aşağıda verilmiştir;

•	“ls” >>> donanım üzerinde tanımlı klasörleri görmeye sağlayacak komuttur. 

•	“ls -alF” >>> komutu ile dizinlerdeki klasörlerin detayları öğrenilmektedir.

•	“cd” >>> Mevcut klasörlerin dizinlerine girmemizi sağlayacak komuttur.  

•	“cd ..” >>> Alt klasör dizinlerinden üst klasör dizinlerine geçmemizi sağlayacak olan komut komutudur. 

•	“mkdir” >>> Bulunulan dizin içerisinde boş klasör oluştmaya yarayan komuttur. Örneğin; “mkdir yeniklasor”

•	“rm -rf” >>> Bulunan dizin içerisinde kod içerisinde tanımlanacak olan klasörü silmemizi sağlar. Örneğin;  “rm -rf yeniklasor”

•	“touch” >>> istediğimiz dosya formatında ilgili dizin içerisinde dosya oluşturabiliyoruz. Örneğin;  “touch yenikla.py”

•	“nano” >>> istediğiniz dosya içeriğini okuma, açma ve yorumlama işlemlerinde kullanılır. Bu bir terminal editörtür.  Örneğin;  “nano yenikla.py”
Editör içerisinde yazdığınız, sildiğiniz veya düzenlediğiniz içeriği kaydetmek için CTRL ve X tuşlarına basmanız gerekmektedir. Gelen menüden “Y” harfine basıp ardından “ENTER”e basmamız gerekmektedir.

“mv” >>> komutu bir dosyayı bir yerden biryere taşımamızı sağlamaktadır. 

“top” >>> bu komut windows’taki görev yöneticisinin Raspberrian işletim sistemi üzerindeki benzeridir. Anlık çalışan komutlar ve görevlerin boyutları, süreleri ve ne kadar memory harcadıkları göstermektedir.

--- Raspberry Pinlerinin Kullanımı ---

GPIO.setmode(GPIO.BCM) >>> Kanal numarası ile çağrı yapılır.

GPIO.setmode(GPIO.BOARD) >>>> Pin numarası ile çağrı yapılır.

GPIO.setup(11, GPIO.IN) >>>> >Input pinlerinin belirlenmesi

GPIO.setup(15, GPIO.OUT) >>>> Output pinlerinin belirlenmesi

ÖRNEK PROGRAM 

Bu programın amacı Raspberry donanımı python yazılım dili ile tanımlayıp butona basılıp basılmama durumu kontrol edilecektir.

import RPi.GPIO as GPIO    >>>> Giriş ve çıkış pinlerinin kütüphanesini tanımladık. GPIO ismi verdik

import time   >>>>

GPIO.setmode(GPIO.BOARD) >>>> Buton tanımları

GPIO.setup(10,GPIO.IN,pull_up_down=GPIO.PUD_DOWN) ) >>>> 10 numaralı pini buton giriş bilgisi için tanımladık. GPIO.PUD_DOWN ile butonun yukarı ve aşağı hareketinde 
okumalar yapacak olduğumuzu sisteme belirttik.

while True:  >>> sonsuz döngü oluşturduk.
    time.sleep(1) >>>> bekleme verdik
    if GPIO.input(10)==GPIO.HIGH: >>>Eğer 10.pinde butona basılma durumu mevcut mudur? 
        print("Butona basilmistir") >>> Butona basıldı ise ekranda 
