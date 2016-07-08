(Everything has been tested on a Shield android TV PRO (500Gb))

# Prepare your SHIELD ANDROID TV
+ Turn the shield on ;) and update it to the last system version (currently Shield Exprience 3.2)
+ Go into Parameters -> About -> click 10 times ont "buil" to activate developer mode
+ In Preferences -> 'Developers options" -> Debugging -> activate "USB Debugging"
+ Connect your shield to a PC 
+ Install Android command line tools (adb and fastboot)
  +  ubuntu

`$sudo apt-get install android-tools-adb android-tools-fastboot`

+ mac

`http://developer.android.com/studio/index.html#mac-tools`
		   
		   
+ Check that everything is OK

`adb devices`

should show your shield is connected

+ Reboot the shield in fastboot mode

`adb reboot bootloader`

+ Unlock shield's bootloader
First : 
	`(sudo) fastboot list devices` should show your shield

Then :
	`(sudo) fastboot oem unlock`
**BEWARE it can take upto several hours**

+ prepare your microSD card : 

`gunzip ./ubuntu14.04_SPOC.img.gz | sudo dd of=<path to sdcard>`

for example

`gunzip ./ubuntu14.04_SPOC.img.gz | sudo dd of=/dev/sdb`

+ Put the microSD card in the back of our shield


# To boot on linux after installation is complete
+ Go into fastboot mode

`adb reboot bootloader`

From a PC connected to your Shield

+ Download boot.img from this repository
+ Boot your Shield on linux using boot.img

`sudo fastboot boot boot.img`
 


