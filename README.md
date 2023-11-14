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
17. Generate Locales using "locale-gen"
18. Move this file into the etc directory using "mv locale.conf /etc"
19. Create a hostname file and add the hostname
20. Move this file into the etc directory using "mv hostname /etc"
21. Create a new initramfs using `mkinitcpio -P`
22. Set the root password using `passwd`
23. Change the type of `/dev/sda1` from Linux to EFI using `parted`
24. Format `/dev/sda1` using `mkfs.ext4 /dev/sda1`
25. Install efibootmgr using "pacman -S efibootmgr"
26. Make the grub config file using `grub-mkconfig -o /boot/grub/grub.cfg`
27. Install LXDE using `pacman -S lxde`
28. Install sudo using "pacman -S sudo"
29. Install zsh and ssh using `pacman`
30. Exit the terminal and shutdown
31. Log in to arch linux with the root user
32. Enable NetworkManager using "Systemctl enable NetworkManager"
33. Type "Startx" in the terminal
34. Create a user for yourself and for Codi
35. Install visudo using "pacman -S vi"
36. Use "sudo visudo" and uncomment the line to allow members of group sudo to execute any command
37. Give the users sudo privliledges with "usermod"
38. Write "zsh" to the .bashrc file
39. Install a DE using "pacman -S firefox"
