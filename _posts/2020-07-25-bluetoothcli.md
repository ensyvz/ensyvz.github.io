---
title: "Ucbirimden Bluetooth Kullanma"
excerpt: "Linux'da ucbirim uzerinden bluetooth acma ve bir aygita baglanma"
tags:
     -linux
     -solution
categories: turkish
---

Linux'da farklı sebeplerden dolayı uçbirimden bluetooth'u çalıştırmak ve bir cihaza bağlanmak istiyorsanız eğer yapmanız gerekenler :
(Ben Arch Linux üzerinden anlatıyorum ancak aynı paketi diğer dağıtımlarda yüklediğinizde de çalışacağını düşünüyorum.) 


AUR'dan bluez-utils paketini yükleyelim.
```shell
yay - S bluez-utils 
```

Bluetooth'u bluez-utils paketinin sağladığı bluetoothctl komutuyla çalıştırıp cihazlar için arama başlatalım.
```shell
bluetoothctl
power on
agent on
default-agent
scan on 
```

Bağlanmak istediğiniz cihaz ekranda MAC adresiyle beraber çıktığında bağlanmak için:
```shell
pair cihazın-mac-adresi 
connect cihazın-mac-adresi 
```

Eğer scan on komutundan sonra notready hatası alırsanız:
```shell
rfkill list 
```
Eğer bloklanmış olan varsa:
```shell
rfkill unblock all 
```

Daha sonrasında scan on komutundan devam edebilirsiniz. 
