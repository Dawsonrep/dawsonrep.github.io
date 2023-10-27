# dawsonrep.github.io
Arch Linux Documentation

1) Recieve VMware access code
2) Install VMware workstation and use access code to log in
3) Go to the download link on the wiki and follow it to install the arch linux iso torrent
4) Install Qbittorent to change the torrent to an iso file
5) Open VMware workstation and create the VM using the arch linux iso file
  * Minimum size = 20GB, Change RAM to 2GB
6) Open Arch Linux VM
  * A problem I ran into was the my AMD virtual environment setting was diabled, so I went into the BIOS settings and reenabled it, and I       was then able to run the VM
7) Exit out and go to the directory VM and add a second line of code to the .vmx file.
  * code = firmware="efi"
8) Verify the boot mode using "cat /sys/firmware/efi/fw_platform_size"
  * Command should return "64"
9) Test internet connection using "ip link"
10) Partition the disks using "fdisk /dev/the_disk_to_be_partitioned"
    * Split into /dev/sda and /dev/sda2, make one +500MB and the other to have the rest
11) Format new partition using "mkfs.ext4 /dev/sda2"
12) Mount sda2 using "mount /dev/sda2 /mnt"
13) Install essential packages using "pacstrap -K /mnt base linux linux-firmware"
