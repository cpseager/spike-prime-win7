# spike-prime-win7

Windows 7 is no longer supported, updated, etc. etc. so LEGO quite rightly don't want to support it, so their Spike Prime Windows 10 installer won't run on Windows 7.

However in the real world lots of schools still use Windows 7 on old laptops etc..

In particular we run our FLL competition teams using dedicated offline (old, donated) Windows 7 laptops.

Fortunately the Spike app will work fine on Windows 7 if you copy it across.

Installation on Windows 7 is a 3 step process:

a) Install on a windows 10 machine and copy the installation folder across to the Windows 7 machine on a USB memory stick.

b) Install the Spike DFU mode (firmware upgrade) USB driver.

c) Install the Spike FS mode (usb serial communication) USB driver. 


The DFU mode driver is available as part of the normal LEGO installation. The FS mode driver is not so obvious, because it actually just uses the existing Windows operating system driver (usbser). So we just need to download/install an extra installation 'inf' file which basically just 'tells' Windows 7 to use the existing driver when Spike is connected. 


In more detail (remember to login as an adminstrator and don't connect the Spike hub to the USB cable yet):


1) Install the spike app on a Windows 10 machine.

2) On the Windows 10 machine copy the entire folder C:\Program Files\SPIKE onto a USB stick. As this is an electron wrapped app everything important is all in that one single folder.

3) Now on the Windows 7 machine copy this folder across to the same location C:\Program Files\SPIKE .

4) Double click on the C:\Program Files\SPIKE\driver\usb\dpinst.exe file. This will install the 'DFU mode' Spike driver.

5) Restart the computer. Yes, you really do have to do this.

6) Connect the Spike to the USB cable and turn it on. Remember which USB port you have used on the computer, as it is best to always use the same one for the cable in the future. Ignore any Windows 'Installing device driver' messages and wait 5 minutes or so (driver update/install will eventually fail). During this time download the Spike FS driver and unzip it in a new folder on your desktop. 

7) Open Device Manager (Start>Run>and type 'Device Manager' to find it)

8) Under 'Unknown Devices' you should now see an entry called 'LEGO Technic Large Hub in FS mode'

9) Right Click on this entry and 'Update Driver Software' then 'Browse My Computer for Driver Software'

10) Browse to the folder you unzipped the Spike FS driver to and then click 'Next'. Ignore the scary 'unsigned driver' warning, this process is quite safe as we are not actually installing a new driver, we are just telling windows to use the existing usbser driver (which is already part of the Windows operating system). Let the installation finish.

11) In Device Manager you should now have a 'Spike USB COM Port' entry in the 'Ports (COM & LPT)' section. The software will **only** work when you can see this entry.

12) On the Windows Desktop right click in an empty space and select 'New'>'Shortcut'. Enter the path  'C:\Program Files\SPIKE\spike.exe' and click Next and then give the shortcut a name ('Spike' would be a good choice!)


That's it!

Double click on the shortcut and you should now have a working Spike system on your Windows 7 computer (USB cable connection). If you are brave you can now waste several hours trying to set up a working Bluetooth connection too, but we would suggest simply sticking to the USB cable.


For information your Spike project files will be saved at 

C:\Users\ [username] \Documents\LEGO Education SPIKE
