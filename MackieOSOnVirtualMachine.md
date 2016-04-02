# Introduction #

I have been trying to boot the Mackie OS on a Virtual Machine, still unscucesfully, but I discovered some things that could help to get it to work,
  * the MBR seems like a win95 Master Boot Record
  * the PME.SYS is the first program the bootloader calls and is the Mackie loader, this program later calls the MackieOS.exe which is a Windows Executable,
  * the program loads some "windows compatibility Layer" which I think is a Layer to be able to execute windows programs without all the tipical windows Setup,
  * At some point, the MackieOS.exe loads or call the System3/Drivers/graphics.bpd which is a Binary Portable Dll, which I think it has the structure like a PE file, It cointains various Dlls (in a hex editor I can see It says "This is a windos NT Dynamic Link Library" ) I think these are drivers, It tries to find the display device and then try to load its driver, then here is where the program fails to continue,
  * graphics.bpd writes a log file in System3/drivers/config/graphics.log where it shows the pci cards detection and the attemp to detect the video card and load its drivers,
  * when I first loaded the OS into a virtual Machine, which emulates a video card with unknown vendor/product id (1234:1111) the program detects the video card but can't load the driver because it doesn't recognize which video card is installed
  * then I tried in various Virtual Machines, like VM Player, Virtual Box, Virtual PC, Bochs,Qemu without success
  * I searched the graphics.bpd and found a list of video cards and its vendor/product id, then i changed some, with the vendor/product of the VM card, and when I boot  the VM the graphics.log showed that it detected the card, but then I tried to load its respective driver, which it wasn't found,
  * when the driver isnt detected, it tries to load "vga.drv" but always says "unable to load vga.drv" I tried to put various vga.drv files(from my system32 and others i downloaded which were the win95 vga.drv and win2000 vga.drv found in the instalation discs, and always says "unable to load vga.drv" then I think It look at some other path to load that files


  * I found a linux that fit on a floopy called "Hardware Detection Tool" so I loaded it into a floppy disk and booted it in the Mackie CPU, and it detected the video card as a Cirrus Logic GD 5434-8 with vendor/product id: 1013:00a8
  * I found that Bochs and QEMU can emulate a cirrus card very similar to the Cirrus in the Mackie CPU (Mackie:1013:00a8 , VM:1013:00b8) and in the graphics.bpd that vendor/product it are included, so maybe it detected a compatible card, but when I boot It says in graphics.log it fails at "attempting to enable write combining" then I searched WTF is this and found is something related to the BIOS, so a program can talk to the Video Card, that option is configurable in some BIOS, but in the VM the BIOS isnt configurable, so I think I need to find a BIOS that than be loaded into the VM and that support write combining, or find a Virtual Machine Program with a BIOS that support write combining...

  * when I booted DOS in a floppy in the Mackie CPU I searched for the graphics.log  and it showed that the driver loaded succesfully, and in the part of "enable write combining" it said "success!" and then displayed the video card data:

Graphics device configuration:
> Manufacturer......... Cirrus Logic
> Chipset.............. CL-GD5434
> Memory............... 1024 Kb
> DAC.................. Cirrus Logic Internal 24 bit DAC
> Clock................ Cirrus Logic Internal Clock
> Memory Clock......... 55 Mhz
> Default Memory Clock. 50 Mhz
> Maximum Memory Clock. 70 Mhz
> Driver Revision...... Build 9
> Driver Build......... May 02 2000
> Certified Version.... 1.04
> Certified Date....... May  3 2000

BIOS header information:
> 'U.@..,.......................1IBM VGA Compatible'
> '..0..1 ..CL-GD543x PCI VGA BIOS Version 1.24b   '
> ' ..Copyright 1992-1995 Cirrus Logic, Inc. All Ri'
> 'ghts Reserved...Copyright 1987-1990 Quadtel Corp'
> '. All Rights Reserved...........................'
> '................................................'

Driver for device 0 loaded successfully!

---


I think if I find a way to enable write combining I would be a step closer to boot the Mackie OS,

  * I found another VM Hypervisor called "Xen" I will try to boot the OS using xen and maybe it can work,













