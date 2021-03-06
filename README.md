# yocto_tutorial_notes_on_raspberrypi4
https://www.youtube.com/watch?v=gn3XGLdfPfY
sudo nano /home/ubuntu/.ssh/known_hosts
# raspberry_pi4_tutorial_notes

Raspberry Pi OS default :
  user is "pi", 
  password is "raspberry". 
  
You can change usr users and change each user's password.


SSH using Linux or Mac OS:
```bash
$ ssh pi@<IP>
```

sudo service ssh restart

You can get there by hitting CTRL+ALT+T from the desktop
auto start ssh in raspberry pi 4
- edit /etc/rc.local
```
     $ sudo nano /etc/rc.local
```
- This script is executed at the end of each multiuser runlevel.
- Make sure that the script will "exit 0" on success or any other value on error.
- add 
```
     # auto start for sshd
     sudo /etc/init.d/ssh start
```

Required Packages for the Host Development System for building yocto project:
- The list of packages you need on the host development system can be large when covering all build scenarios using the Yocto Project. 
- This section provides required packages according to Linux distribution and function.

1.3.2.1 Ubuntu and Debian:
- The following list shows the required packages by function given a supported Ubuntu or Debian Linux distribution:

# Note:
- If your build system has the oss4-dev package installed, 
- you might experience QEMU build failures due to the package installing its own custom /usr/include/linux/soundcard.h on the Debian system. 
- If you run into this situation, either of the following solutions exist:
```
     $ sudo apt-get build-dep qemu
     $ sudo apt-get remove oss4-dev
 ```                   
# Essentials: 
- Packages needed to build an image on a headless system:
```
     $ sudo apt-get install gawk wget git-core diffstat unzip texinfo gcc-multilib build-essential chrpath socat
```
- run output in pi4
```
Reading package lists... Done
Building dependency tree
Reading state information... Done
Note, selecting 'git' instead of 'git-core'
Package gcc-multilib is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'gcc-multilib' has no installation candidate
```

Graphical and Eclipse Plug-In Extras: Packages recommended if the host system has graphics support or if you are going to use the Eclipse IDE:

     $ sudo apt-get install libsdl1.2-dev xterm
                        
Documentation: Packages needed if you are going to build out the Yocto Project documentation manuals:

     $ sudo apt-get install make xsltproc docbook-utils fop dblatex xmlto
                        
ADT Installer Extras: Packages needed if you are going to be using the Application Development Toolkit (ADT) Installer:

     $ sudo apt-get install autoconf automake libtool libglib2.0-dev libarchive-dev
                        
OpenEmbedded Self-Test (oe-selftest): Packages needed if you are going to run oe-selftest:

     $ sudo apt-get install python-git
                        
