# mineekJB
(theoretical) 15.0-15.5b4 checkm8-based "jailbreak"

## Warning: I AM NOT RESPONSIBLE FOR ANY DATA LOSS WHATSOEVER, OK? IF U MESS UP AND NEED TO RESTORE, IT'S NOT MY FAULT.

### What does it do now?
Well, for now it installs Procursus rootless bootstrap into /var/jb and drops a loader app into tips.app. From there you can install app-based DEB tweaks ( not all work atm ) and trollstore ( with permission from opa334 ) and NewTerm2

### What does it NOT do?
tweak injection ( which means that you cant run tweak-tweaks )

stability

### ok this is all fun and games but how do i run this?
Please, dont come to me asking for help, as I've stated multiple times its meant to be DEV ONLY. If u want a more usable jailbreak, check out cheyote / Fugu15.

You need theos / xcode 12.4+

Basically FIRST make yourself a custom kernel with amfi patched. ( working on automating this )

Then make yourself an ssh ramdisk using [SSHRD_Script](https://github.com/verygenericname/SSHRD_Script) and copy the files from the sshramdisk folder into installer/sshramdisk.

Then edit install.sh with the right file names / ipsw link. ( can find on theiphonewiki )

then run in the root of the repo
1. ```./build.sh```
2. ```cd installer```
3. ```./install.sh```
4. now pwn your device with gaster for example
5. then boot the ramdisk by using ```cd sshramdisk && ./boot(A10+).sh```
6. After its done your device will reboot automatically, put it in pwnDFU again
7. Boot the kernel with patched amfi and open Tips app and enjoy!

( recommended to follow post-install to install sileo )

### FAQ:
#### Why jailbreak in quotes?
Because it isnt a full jailbreak, it doesnt have Libhooker for example. This is like the bare minimum.

#### How do i install tweaks?
You can install tweaks by using sileo.

#### Where is the code?
I still need to add the finishing touches to it, this will take maybe 4 - 6 days or something, once thats done I'll publish it here.

### Post-install
1. Open NewTerm2
2. ```/var/hardware/TrollTerm/bin/sudo /var/jb/usr/bin/bash```
3. ```source /var/jb/etc/profile```
4. ```mount -uw /private/preboot```
5. ```/var/jb/prep_bootstrap.sh```
6. ```cd /var/mobile```
7. ```dpkg -i sileo.deb```


### Why so hard to install?
Well, im working on making it easier, as i've stated already, its mostly for devs and people with some experience. Keep an eye out on this repo for updates :)

### Credits List:
galaxy#0007 - Compiled the bootstrap.

[nebula](https://github.com/itsnebulalol/) - Helping me with getting NewTerm working.

[opa334](https://github.com/opa334/) - Giving me permission to use some of their [trollstore](https://github.com/opa334/TrollStore) code here. ( Like the whole root helper is mostly trollstorehelper so huge props! )

[nathan](https://github.com/verygenericname) - Code inspiration from [SSHRD_Script](https://github.com/verygenericname/SSHRD_Script)

Coldi#0001 - Giving me support throughout this project.

Nick Chan#0001 - Helping with getting sileo working

And so much more people who did little things :)
