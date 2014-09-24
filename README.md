Free Law Project's Free Law Machine is a virtual machine created for
developers of software for the Free Law Project. It is preconfigured to
get developers working on CourtListener, juriscraper, or other Free Law
Project efforts. Here's how to get it running:

How to Run the Free Law Project VM in 10 Easy Steps!

Note: Be sure virtualization support is not turned off in your BIOS. Some
    laptops come this way.

1. Download .zip from https://www.courtlistener.com/tools/free-law-machine/
   You can ensure your download worked by checking the value of the sha1 sum
   in sha1.txt.
2. On Linux we have run into problems with kernels other than 3.5. If you 
   encounter stability issues, you may want to investigate compiling the 3.5.0
   kernel from http://www.kernel.org/pub/linux/kernel/v3.x/linux-3.5.tar.xz
   on your host machine.
3. Unzip our .zip file
4. Download the free VMware Player: https://www.vmware.com/products/player/
5. Install the VMware Player (chmod u+x the vmware file and run it as root)
6. Open VMware Player (as a non-root user): vmplayer &
7. Click 'Open a Virtual Machine'
8. Browse to the folder where you extracted our .zip file
9. You should see the file in a VMware virtual machine config. Double click it.
10. The virtual OS should boot now. (Ubuntu login password is 'freelaw')

Free Law Machine, brought to you by Free Law Project: http://freelawproject.org
