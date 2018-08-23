# Bodhi Builder on Ubuntu 16.04

Bodhibuilder is a fork of the old Remastersys script, it has been tuned to create a bootable live ISO of your Bodhi Linux OS or Ubuntu based derivatives. There are 2 types of modes available: backup mode and distribution mode.

Backup mode creates a copy of your running OS so that the live ISO will require you to login using your credentials and the desktop will be your same desktop you've created it to be. There's your familiar desktop, menu, and programs at your fingertips, in a live portable ISO!

Distribution mode will also create a copy of your running OS, but will not keep your desktop or any personal settings. It will create a live ISO with all of your programs, but, unlike backup mode, your personal information (like login info) will not be contained in the ISO. Share this with your friends so they can install your newly created OS!

=== Releases ===

```sh
bodhibuilder_2.1.x.deb --> stable release (Ubuntu 14.04)
bodhibuilder_2.2.x.deb --> stable release (Ubuntu 16.04)
```
## Features
* These are the features of the stable build --> bodhibuilder_2.2.x :
* Used to create Bodhi Linux 4.x (not compatible with earlier versions of Bodhi 3.x, 2.x or 1.x)
* Compatible with 32 and 64 bit operating systems of Ubuntu 16.04 derivatives (not compatible with earlier versions due to some package name and file location changes)
* UEFI support for 64 & 32-bit using xorriso
* Offline installation from your created ISO
*  xz compression on the squashfs
*  Custom GRUB name
*  New folder & file exclusion function
*  dd or cat > direct to USB for best booting results
*  Ability to include only specific icon sets and languages to cut down on ISO size
* I have successfully created 8Gb+ ISO's that will live boot off of USB.

## Installation 

Step 1. Download Bodhi Builder from following link

```sh
https://sourceforge.net/projects/bodhibuilder/files/latest/download
Save file {My download directory path is /home/ubuntu/Downloads/ }
```  
Step 2. We can Install bodhibuilder by two ways  
* via Graphically  
* via Terminal (I have used this method and I recommend to use this for fast execution)
  
####Graphically
Step 2.1. We are going to install bodhibuilder graphically so Initially open the folder where bodhibuilder.deb file is stored.After that, right click on the given file and choose the first option i.e. "Open With Software install"
(For reference use following image):

Step 2.2. Now click on "install" button

Step 3. Now, Click on Windows button or move to "Search in Computer". After that search and click "Bodhibuilder". To open BodhiBuilder System will ask password.
![Bodhi](1.png"Builder")
Step 4. After password authentication, a window will pop-up which is bodhibuilder.
Step 4. During the process we have to close all other process as per instruction given by bodhibuilder.And at the last Click on second option i.e. "dist".
![dist](4.png "dist")  

Press "Ok" to create a (.iso) file.  
* Note: It will take time, to create (.iso) file.(.iso)file will be created on bodhibuilder folder situated in /home. 

####Via Terminal
Step 2.1. Open terminal (ctrl+alt+t) and type the following (Note: Check the path ).  

```sh
  $ sudo dpkg -i /home/ubuntu/Downloads/BodhiBuilder* sudo apt-get install -f
```

It will ask for password.  

Step 3. To Create a (.iso) file type the following command  

```sh
  $ sudo bodhibuilder -d
```

* Note : the above command takes time for excecution.wait until it completes the whole process.  
* "-d " is for dist [custom .iso]  
{for more information use "man bodhibuilder"}.  

Step 4. At the last the (.iso) file is created in "/home/bodhibuilder/bodhibuilder/" directory.  

```sh
  $ ls /home/bodhibuilder/bodhibuilder/*.iso
``` 














