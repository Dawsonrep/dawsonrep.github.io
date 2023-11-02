# Dawsonrep.github.io
**Arch Linux Documentation**

1. Receive VMware access code
2. Install VMware Workstation and use access code to log in
3. Go to the download link on the wiki and follow it to install the Arch Linux ISO torrent
4. Install Qbittorrent to change the torrent to an ISO file
5. Open VMware Workstation and create the VM using the Arch Linux ISO file
   - Minimum size = 20GB, Change RAM to 2GB
6. Open Arch Linux VM
   - A problem I ran into was that my AMD virtual environment setting was disabled, so I went into the BIOS settings and reenabled it, and I was then able to run the VM
7. Exit out and go to the directory VM and add a second line of code to the .vmx file.
   - Code = firmware="efi"
8. Verify the boot mode using `cat /sys/firmware/efi/fw_platform_size`
   - Command should return "64"
9. Test internet connection using `ip link`
10. Partition the disks using `fdisk /dev/the_disk_to_be_partitioned`
    - Split into `/dev/sda` and `/dev/sda2`, make one +500MB and the other to have the rest
11. Format the new partition using `mkfs.ext4 /dev/sda2`
12. Mount `/dev/sda2` using `mount /dev/sda2 /mnt`
13. Bind mount essential directories
14. Chroot into Arch using `arch-chroot /mnt`
15. Install nano using `pacman -Sy nano`
16. Create `locale.conf` and add the line "LANG=en_US.UTF-8"
17. Create a hostname file and add the hostname
18. Create a new initramfs using `mkinitcpio -P`
19. Set the root password using `passwd`
20. Change the type of `/dev/sda1` from Linux to EFI using `parted`
21. Format `/dev/sda1` using `mkfs.ext4 /dev/sda1`
22. Make the grub config file using `grub-mkconfig -o /boot/grub/grub.cfg`
23. Install LXDE using `pacman -S lxde`
24. Create users for `codi` and `dawson` with sudo permissions
25. Install zsh and ssh using `pacman`
26. Add color coding using `PS1='\[\e[1;34m\]\u\[\e[0m\]@\[\e[1;32m\]\h:\[\e[1;36m\]\w\[\e[0m\]\$ '`
