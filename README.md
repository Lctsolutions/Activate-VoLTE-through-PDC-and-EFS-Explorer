# Activate-VoLTE-through-PDC-and-EFS-Explorer (Android 11 | Android 12 | Android 12.1 | Android 13)
If you want to activate VoLTE on custom rom (in my case it's crDroid 8 and crDroid 9) (Root needed) without going to OOS 11 / OOS 12: 

1. Download and install QPST and Qualcomm Drivers from releases page
2. Download and install USB Gadget Tool from https://f-droid.org/ru/packages/net.tjado.usbgadget/
3. Plug-in your phone into PC, and don't forget to enable MTP and ADB
4. Open USB Gadget Tool and turn on next modes (if they turned off) : 
     
     ( cser.dun.0 , diag.diag, diag.diag.mdm , ffs.adb , gsi.dpl , gsi.rmnet , qdss.qdss , qdss.qdss.mdm )
     
     
5. Further actions depending on what you need: EFS or PDC
6. IMPORTANT!!! Don't forget to disconnect and reboot your OP7Pro after using any mode (If you want use both EFS and PDC, then use PDC, after that, disconnect and reboot OP7Pro, then repeat all steps from beginning for EFS


========================================================================================

For EFS Explorer

Excecute " setprop sys.usb.config diag,diag_mdm,qdss,qdss_mdm,serial_cdev,dpl,rmnet,adb " in adb shell with su (root):

adb shell
su
setprop sys.usb.config diag,diag_mdm,qdss,qdss_mdm,serial_cdev,dpl,rmnet,adb

Then check that all COM ports are added in QPST Configuration, one of these ports will be SDM855 - our device

Open EFS Explorer

Profit

End of guide for EFS Explorer

========================================================================================

NOW THE MOST INTERESTING THING

========================================================================================

For PDC Tool

Excecute " setprop sys.usb.config diag,serial_cdev,rmnet,adb " in adb shell with su (root):

adb shell
su
setprop sys.usb.config diag,serial_cdev,rmnet,adb

Then after 10 seconds disable in USB Gadget Tool app next modes : "diag.diag and diag.diag.mdm" 

After that open PDC Tool

Profit

End of guide for PDC Tool
