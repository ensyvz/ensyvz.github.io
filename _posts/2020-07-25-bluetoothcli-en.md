---
title: "Bluetooth Using Terminal"
excerpt: "Connecting to a device with bluetooth using terminal."
tags:
     -linux
     -solution
     -english
---

You may want to use terminal for connecting to bluetooth devices and here is how:
(I am explaining over Arch Linux but when you install the necessary package you should be able to do same thing in other distros.)

Install bluez-utils package from AUR.
```shell
yay - S bluez-utils 
```
Get bluetooth up and running using bluetoothctl command provided by bluez-utils.
```shell
bluetoothctl
power on
agent on
default-agent
scan on 
```

When the device that you want to connect shows up with MAC Adress on screen, do following step.
```shell
pair device-mac-adress 
connect device-mac-adress 
```

If an error shows up that says notready after running scan on command do following steps.
```shell
rfkill list 
```

If there is any blocked ones run this command.
```shell
rfkill unblock all 
```

Daha sonrasında scan on komutundan devam edebilirsiniz. 
