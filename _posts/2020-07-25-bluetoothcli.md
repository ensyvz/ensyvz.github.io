---
title: "Ucbirimden Bluetooth Kullanma"
excerpt: "Linux'da ucbirim uzerinden bluetooth acma ve bir aygita baglanma"
tags:
     -linux
     -solution
---

Linux'da farklı sebeplerden dolayı uçbirimden bluetooth'u çalıştırmak ve bir cihaza bağlanmak istiyorsanız eğer yapmanız gerekenler :
(Ben Arch Linux üzerinden anlatıyorum ancak aynı paketi diğer dağıtımlarda yüjlediğinizde de çalışacağını düşünüyorum.) 


AUR'dan bluez-utils paketini yükleyelim.
```shell
yay - S bluez-utils 
```

Bluetooth'u bluez-utils paketinin sağladığı bluetoothctl komutuyla çalıştırıp cihazlar için arama başlatalım.
```shell
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
