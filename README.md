# Raspberry-Pi-Setup

https://www.raspberrypi.com/products/raspberry-pi-4-model-b/ cihazı üzerinde;

---Elimizdeki cihaz hakkında---
4GB RAM,
2.4GHZ ve 5GHZ destekleyen IEEE 802.11ac WiFi ve Bluetooth 5.0 modülü,
Gigabit Ethernet Portu,
2 Adet Usb 3.0 Girişi,
2 Adet Usb 2.0 Girişi,
2 Adet Micro HDMI Portu,
Micro-SD Kart Yuvası ve
Standart 40 Pin Yapısı bulunmaktadır.
Ayrıca bu cihazın güç kontrolü için USB-C Tipi Güç Girişinden 5v 3A besleme gerekmektedir.

---Kurulum Adımları---
Kurulum İşlemleri İçin Gerekenler;
•	SD Kart Fomatter Yazılımı (Kurulum yapılacak SD kartın fortmanlana bilmesi için kullanılacaktır)
•	https://www.raspberrypi.com/software/operating-systems/ linki üzerinden; Raspberry Pi tavsiye edilen kurulum (recommended software) dosyasını indiriyoruz. İndirilecek *.iso dosyasını bilgisayarda bir konuma kayıt edin. Örneğin masaüstüne.
•	Win32 Disk Manager yazılımı ile formatlanan SD karta *.iso dosyasını yazdırıyoruz. Ortalama 10-15 dakikalık kurulumdan sonra SD kartı Raspberry’e takıp çalıştırıyoruz. 
---Kurulum İşlemleri Tamamlandı---

Kurulum işlemleri tamamlandıktan sonra ayarlar ve yapılandırma işlemleri gerekmektedir. Bu işlemler sırası ile;

--- Ayarlar ---
Menü’den  Preferences  “Rasberry Pi Configuration” bölümünü açıyoruz. 
•	Raspberry üzerinde ayarlar ve yapılandırmalar açılan menü/pencere üzerinde olacaktır.
•	İlgili Menunun detaylı anlatım ve görsel içerikleri bu link üzerindedir https://www.raspberrypi.com/documentation/computers/configuration.html 
•	Raspberry üzerinde açılan menü “Raspberry Pi Configuration” Raspberry donanımı üzerinde açılıp kapanmasını istediğiniz portlar, görüntü ayarları, arayüz ayarları, şifre işlemleri, donanım performans ayarları, konum işlemlerine bağlı olarak saat ve gün ve wifi ayarlarını yapılabilmektedir. İlgili menülerin aktif veya pasif yaptıktan sonra donanım resetlenmek isteyecektir. Onayınız sonrası sistem yeniden başlatılacaktır. 
DİP NOT: Açıp kapattığınız ayarları bir noktalara kaydetmenizi tavsiye ederim. Raspberry üzerinde oluşabilecek hatalar anında hangi ayarı açıp-kapattığınızı bilmelisiniz. Hangi sensörün portunu ilgili projenizde kullanacaksanız o zaman aktif veya pasif yapın!!!!!! Ayrıca kapatıp açtığınız port ve ayarlar sistemin kilitlenmesine neden olabilir. O zaman SDkarta yeniden kurulum yapmanız gerekmektedir. Bu konuda internette araştırma yaparak daha net sonuçlara erişebiliriz. Tek bir blog sayfasını ele alarak işlem yapmayın!!!!!!

--- Ayarlar Tamamlandı ---

Raspberry Pi’yi kendi donanımına bağlı klavye,mause ve monitör ile veya uzaktaki bir cihazdan yönetmenize imkan tanımaktadır. Uzaktan bağlanma durumunda “Raspberry Pi Configuration”  bölümünden SSH ve VNC etkinleştirmesi gerekmektedir. 
“Raspberry Pi Configuration”   Interfaces  SSH  Enable seçerek uzaktan erişimi aktif hale getiriyoruz. 
•	Komut satırından sudo raspi-config  5 Interfacing Options  P2 SSH  ENABLED  YES işlem adımları ile SSH’ı aktif hale getirebilmekteyiz. 
•	sudo systemctl status ssh  yazıldığında “active (running)” ifadesinin görülmesi gerekmektedir.  
•	VNC arayüzünü bağlantı kurmak için kullanacağız. “Raspberry Pi Configuration”   Interfaces  VNC  Enable seçerek erişimi aktif hale getiriyoruz.
•	Komut satırından sudo raspi-config  5 Interfacing Options  P3 VNC  ENABLED  YES işlem adımları ile VNC’yi aktif hale getirebilmekteyiz. 
Bu işlemler ile Raspberry yanınızda olmadığında modemden Raspberry’e port açıp uzaktan bağlantı sağlayabiliyoruz.

<<<<<<<<<<<Devamı Gelecek>>>>>>>>>>>>
