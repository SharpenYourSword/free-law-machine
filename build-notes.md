Before *shutting down* the VM (do not suspend), make sure:

- Trash is empty.
- Downloads directory is empty.
- Intellij and Firefox were closed with the correct tabs open.
- Any nefarious Firefox history has been purged.
- Apt is cleaned out:

        sudo apt-get clean
        sudo apt-get autoclean
        sudo apt-get autoremove

- If the output from `df -h` is significantly different than the size of the
  vmdk file, you can fix this by first filling the virtual drive with zeroes 
  and then removing the zero-filled file. This requires slightly more space 
  (about 2GB more) than the current size of the vmdk, but can shrink the vmdk
  significantly. To do this process:
   
      sudo su
      cat /dev/zero > wipefile; rm -f wipefile
      shutdown -h now
  
 Then, in the VMware Player, go to the machine's settings > Hard Disk > 
 Utilities > Compact...
   
 
Once complete, create the zip file by:

 1. Combining the vmdk, nvram and vmx files.
    - The vmdk file should be slightly larger than the size on disk, around 
      8-9GB.
 1. Name the file: free-law-virtual-machine-vXX.zip
 1. Push that to the server using rsync and a command like:

         rsync -a --partial --append --progress free-law-virtual-machine-v*.zip courtlistener.com:/home/mlissner/

    (This command can then be re-run as necessary to restart the push.)
 1. Move the file to the correct directory
 
         sudo mv free-law-virtual-machine-v1.1.zip /sata/vm
         sudo chown www-data:www-data free-law-virtual-machine-v1.1.zip

 1. Update the sha1 file by running:
 
         sha256sum free-law-virtual-machine-v{your-version}.zip >> sha2.txt
 
 1. Finally, check it in, and push it up to git.
 
         sudo -u www-data git commit -m "New version released!"
         sudo -u www-data git push
     
