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
	`(sudo) fastboot devices` should show your shield

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
 

# Useful information 
+ user/passwd are spoc/SPOC
+ opam (OCaml PAckage Manager) is installed :
```
opam list
 # Installed packages for 4.02.3:
 base-bigarray            base  Bigarray library distributed with the OCaml compiler
 base-bytes               base  Bytes library distributed with the OCaml compiler
 base-ocamlbuild          base  OCamlbuild binary and libraries distributed with the OCaml compiler
 base-threads             base  Threads library distributed with the OCaml compiler
 base-unix                base  Unix library distributed with the OCaml compiler
 biniou                  1.0.9  Binary data format designed for speed, safety, ease of use and backward compatibility as
 camlp4                 4.02+1  Camlp4 is a system for writing extensible parsers for programming languages
 cmdliner                0.9.8  Declarative definition of command line interfaces for OCaml
 conf-m4                     1  Virtual package relying on m4
 conf-pkg-config           1.0  Virtual package relying on pkg-config installation.
 conf-which                  1  Virtual package relying on which
 cppo                    1.3.2  Equivalent of the C preprocessor for OCaml programs
 ctypes                  0.6.2  Combinators for binding to C libraries without writing any C.
 ctypes-foreign          0.4.0  Virtual package for enabling the ctypes.foreign subpackage.
 easy-format             1.2.0  High-level and functional interface to the Format module of the OCaml standard library
 merlin                  2.5.0  Editor helper, provides completion, typing and source browsing in Vim and Emacs
 ocamlbuild                  0  Build system distributed with the OCaml compiler since OCaml 3.10.0
 ocamlfind               1.6.2  A library manager for OCaml
 ocp-build        1.99.17-beta  Project manager for OCaml
 ocp-indent              1.5.3  A simple tool to indent OCaml programs
 typerex-build    1.99.17-beta  Project manager for OCaml
 yojson                  1.3.2  Yojson is an optimized parsing and printing library for the JSON format
```
 

# Thanks
+XDA forums and particularly  
	+ [Ubuntu Utopic for nvidia shield tv](http://forum.xda-developers.com/shield-tv/general/ubuntu-utopic-nvidia-shield-tv-t3150352/)
	+ [Build kernel from source and boot to Ubuntu using L4T (Linux for Tegra) rootfs](http://forum.xda-developers.com/shield-tv/general/build-kernel-source-boot-to-ubuntu-t3274632)

