# Docker-IOT Using Arduino Uno And Johnny-Five Tranform Your IOT Platform to Next level 
![](/Webp.net-resizeimage.jpg)

# Prerequisites

At least an Arduino or compatible board (Uno, Mega, Leonardo, Fio, Pro, Pro Mini)

```Arduino UNO
Arduino Leonardo
Arduino MEGA
Arduino FIO
Arduino Pro
Arduino Pro Mini
TinyDuino
```
Sparkfun Inventor's Kit (Recommended for getting started)
# OSX
````
Install Node.js >= 0.10.x
Install Xcode
Install node-gyp npm install -g node-gyp
````
# Windows

Via @ThomasDeutsch on https://github.com/rwldrn/johnny-five/issues/48#issuecomment-7696662
```
Install Node.js >= 0.10.x 32 bit (unless anyone can confirm success with 64 bit)
npm --add-python-to-path install --global --production windows-build-tools
Install node-gyp npm install -g node-gyp
```
# Ubuntu and Debian
```
Install Node.js >= 0.10.x apt-get install nodejs
Install the nodejs-legacy package apt-get install nodejs-legacy
Install build-essential or a suitable alternative apt-get install build-essential
```
# Arch Linux
```
Install Node.js pacman -S nodejs
Install Arduino Libraries (for firmware flashing) pacman -S arduino

```
# Hello World

Generally Arduino boards (Uno, Mega, Leonardo, Fio, Mini) come pre-flashed with the compiled StandardFirmata firmware. In most cases, getting started is as simple as...
```
mkdir nodebot && cd nodebot;

npm install johnny-five;

```
Now open your text editor and create a new file called "strobe.js", in that file type or paste the following:
```
var five = require("johnny-five"),
    board = new five.Board();

board.on("ready", function() {
  // Create an Led on pin 13
  var led = new five.Led(13);

  // Strobe the pin on/off, defaults to 100ms phases
  led.strobe();
});
```
Make sure the board is plugged into your host machine (desktop, laptop, raspberry pi, etc). Now, in your terminal, type or paste the following:
```
node strobe.js
Troubleshooting
```
# Firmware

The StandardFirmataPlus firmware is the one that is used for Johnny-Five to communicate with the board. That means you have to install it first, then you can execute the nodejs programs. Arduiono IDE
```
Open Arduino IDE
Verify correct port and board
Navigate to File > Examples > Firmata > StandardFirmataPlus
Load sketch onto board.
Packaged
```
Install arduino package on your operating system ).
Make a firmware folder and save this firmware.ino into it. if the link is dead again and not appearing in the Arduino IDE, use this gist backup.
Install arduino libraries via arduino --install-library "Firmata,Servo" in the Terminal.
Flash the arduino board via arduino --board "arduino:avr:uno" --upload ./path/to/firmware/firmware.ino. Remember to change your board according to what you use. See below on how to figure out that identifier.
If the upload was successful, the board is now prepared for johnny-five usage.
Finding out your Board identifier for arduino-tools

Go to the package index file of the Arduino tools.
Download the url entry of the package that contains your boards, for example http://downloads.arduino.cc/cores/avr-1.6.18.tar.bz2.
Inside the archive, there's a boards.txt file that contains all supported boards. These boards can be used as the last part of the identifier. For example, the boards.txt lists yun meaning the arduino --board "arduino:avr:yun" has to be used.
List of Arduino Board identifiers (May 2017)

This is a compiled list that may not be up-to-date. Use the method described above in case you can't find your board here.
```
"arduino:avr:yun" for Arduino Yun
"arduino:avr:uno" for Arduino/Genuino Uno
"arduino:avr:diecimila" for Arduino Duemilanove or Diecimila
"arduino:avr:nano" for Arduino Nano
"arduino:avr:mega" for Arduino/Genuio Mega or Mega 2560
"arduino:avr:megaADK" for Arduino Mega ADK
"arduino:avr:leonardo" for Arduino Leonardo
"arduino:avr:leonardoeth" for Arduino Leonardo ETH
"arduino:avr:micro" for Arduino/Genuino Micro
"arduino:avr:esplora" for Arduino Esplora
"arduino:avr:mini" for Arduino Mini
"arduino:avr:ethernet" for Arduino Ethernet
"arduino:avr:fio" for Arduino Fio
"arduino:avr:bt" for Arduino BT
"arduino:avr:LilyPadUSB" for LilyPad Arduino USB
"arduino:avr:lilypad" for LilyPad Arduino
"arduino:avr:pro" for Arduino Pro
"arduino:avr:atmegang" for Arduino NG or older
"arduino:avr:robotControl" for Arduino Robot Control
"arduino:avr:robotMotor" for Arduino Robot Motor
"arduino:avr:gemma" for Arduino Gemma
"arduino:avr:circuitplay32u4cat" for Arduino Circuit Playground
"arduino:avr:yunmini" for Arduino Yun Mini
"arduino:avr:chiwawa" for Arduino Industrial 101
"arduino:avr:one" for Linino One
"arduino:avr:unowifi" for Arduino Uno WiFi
Other
```
Sometimes Windows systems will fail to compile native dependencies, if you run across this case try:

```npm install johnny-five --msvs_version=2012```



# Step 1:
```Install Docker Machine
Install VirtualBox
```

# Step 2:
Create your local docker-machine VM
```
$ docker-machine create local -d virtualbox
```
# Step 3:
Stop your Docker VM
```$ docker-machine stop local ```
Now, open VirtualBox

![](/vm1.png)

Go to settings and mount your Arduino

![](/vm2.png)
```
Biradars-Air-2:~ sangam$ docker run -ti --privileged node /bin/bash
Unable to find image 'node:latest' locally
latest: Pulling from library/node
c5e155d5a1d1: Pull complete 
221d80d00ae9: Pull complete 
4250b3117dca: Pull complete 
3b7ca19181b2: Pull complete 
425d7b2a5bcc: Pull complete 
69df12c70287: Pull complete 
9b754a1bcda7: Pull complete 
74b273083e97: Pull complete 
Digest: sha256:3d4411d1933dc93e78b9e0de556a22178269952b98cbbea7ca935d890527ae27
Status: Downloaded newer image for node:latest
root@14801ba53858:/# mkdir test && cd test
root@14801ba53858:/test# npm install johnny-five

> @serialport/bindings@2.0.8 install /test/node_modules/@serialport/bindings
> prebuild-install --tag-prefix @serialport/bindings@ || node-gyp rebuild

npm WARN saveError ENOENT: no such file or directory, open '/test/package.json'
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN enoent ENOENT: no such file or directory, open '/test/package.json'
npm WARN test No description
npm WARN test No repository field.
npm WARN test No README data
npm WARN test No license field.

+ johnny-five@1.1.0
added 95 packages from 55 contributors and audited 303 packages in 20.844s
found 0 vulnerabilities

root@14801ba53858:/test# apt-get update && apt-get install -y vim
Ign:1 http://deb.debian.org/debian stretch InRelease
Get:2 http://deb.debian.org/debian stretch-updates InRelease [91.0 kB]
Get:3 http://security.debian.org/debian-security stretch/updates InRelease [94.3 kB]        
Get:4 http://deb.debian.org/debian stretch Release [118 kB]                                 
Get:5 http://deb.debian.org/debian stretch-updates/main amd64 Packages [31.7 kB]         
Get:6 http://security.debian.org/debian-security stretch/updates/main amd64 Packages [492 kB]
Get:7 http://deb.debian.org/debian stretch Release.gpg [2434 B]               
Get:8 http://deb.debian.org/debian stretch/main amd64 Packages [7082 kB]
Fetched 7912 kB in 18s (417 kB/s)                                                                                                             
Reading package lists... Done
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  libgpm2 vim-common vim-runtime xxd
Suggested packages:
  gpm ctags vim-doc vim-scripts
The following NEW packages will be installed:
  libgpm2 vim vim-common vim-runtime xxd
0 upgraded, 5 newly installed, 0 to remove and 3 not upgraded.
Need to get 6766 kB of archives.
After this operation, 31.2 MB of additional disk space will be used.
Get:1 http://deb.debian.org/debian stretch/main amd64 xxd amd64 2:8.0.0197-4+deb9u1 [132 kB]
Get:2 http://deb.debian.org/debian stretch/main amd64 vim-common all 2:8.0.0197-4+deb9u1 [159 kB]
Get:3 http://deb.debian.org/debian stretch/main amd64 libgpm2 amd64 1.20.4-6.2+b1 [34.2 kB]
Get:4 http://deb.debian.org/debian stretch/main amd64 vim-runtime all 2:8.0.0197-4+deb9u1 [5407 kB]
Get:5 http://deb.debian.org/debian stretch/main amd64 vim amd64 2:8.0.0197-4+deb9u1 [1034 kB]                                                 
Fetched 6766 kB in 10s (625 kB/s)                                                                                                             
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package xxd.
(Reading database ... 29980 files and directories currently installed.)
Preparing to unpack .../xxd_2%3a8.0.0197-4+deb9u1_amd64.deb ...
Unpacking xxd (2:8.0.0197-4+deb9u1) ...
Selecting previously unselected package vim-common.
Preparing to unpack .../vim-common_2%3a8.0.0197-4+deb9u1_all.deb ...
Unpacking vim-common (2:8.0.0197-4+deb9u1) ...
Selecting previously unselected package libgpm2:amd64.
Preparing to unpack .../libgpm2_1.20.4-6.2+b1_amd64.deb ...
Unpacking libgpm2:amd64 (1.20.4-6.2+b1) ...
Selecting previously unselected package vim-runtime.
Preparing to unpack .../vim-runtime_2%3a8.0.0197-4+deb9u1_all.deb ...
Adding 'diversion of /usr/share/vim/vim80/doc/help.txt to /usr/share/vim/vim80/doc/help.txt.vim-tiny by vim-runtime'
Adding 'diversion of /usr/share/vim/vim80/doc/tags to /usr/share/vim/vim80/doc/tags.vim-tiny by vim-runtime'
Unpacking vim-runtime (2:8.0.0197-4+deb9u1) ...
Selecting previously unselected package vim.
Preparing to unpack .../vim_2%3a8.0.0197-4+deb9u1_amd64.deb ...
Unpacking vim (2:8.0.0197-4+deb9u1) ...
Processing triggers for mime-support (3.60) ...
Setting up xxd (2:8.0.0197-4+deb9u1) ...
Setting up libgpm2:amd64 (1.20.4-6.2+b1) ...
Processing triggers for libc-bin (2.24-11+deb9u4) ...
Setting up vim-common (2:8.0.0197-4+deb9u1) ...
Setting up vim-runtime (2:8.0.0197-4+deb9u1) ...
Processing triggers for hicolor-icon-theme (0.15-1) ...
Setting up vim (2:8.0.0197-4+deb9u1) ...
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vim (vim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vimdiff (vimdiff) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rvim (rvim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rview (rview) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vi (vi) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/view (view) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/ex (ex) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/editor (editor) in auto mode
root@14801ba53858:/test# 
```

![](/ezgif.com-gif-maker.gif)
