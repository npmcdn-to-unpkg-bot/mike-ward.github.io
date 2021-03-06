---
layout: post
title: 'Windows 7 Bluetooth Mouse Fix'
---
I’ve had this weird problem on my new laptop where the Bluetooth mouse stops working. Sometimes using the scroll wheel reactivates it but most of the time I have to turn off, and then turn on the Bluetooth radio (FAIL). I was sure it had something to do with the power management on the mouse. After a few hours of fiddling I found that it was indeed a power management setting, but for the Bluetooth adapter, not the the mouse. Here’s a quick tutorial on how to disable the power management for Bluetooth devices on Windows 7.

Right click on “Computer” on the desktop or in the start menu and select properties. You should see a something similar to below:

![Windows 7 properties windows](/cdn/images/blog/Windows7BluetoothMouseFix_8F55/Capture.jpg)

Select Device Manager (yellow highlight). Expand the Bluetooth Radios item and select the Bluetooth device.

![Capture2](/cdn/images/blog/Windows7BluetoothMouseFix_8F55/Capture2.jpg)

Uncheck the “Allow the computer to turn off this device to save power”

![Capture3](/cdn/images/blog/Windows7BluetoothMouseFix_8F55/Capture3.jpg)

It’s likely the dialog windows on your computer will be slightly different than the ones pictured here but the general idea is the same.
