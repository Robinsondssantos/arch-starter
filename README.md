## 1 - loadkeys br-abnt2
## 2 - fdisk -l
## 3 - fdisk /dev/sda
## 4 - cfdisk /dev/sda


partions linux (/mnt), linux swap (SWAP)


## 5 - mkfs.ext4 /dev/sda1
## 6 - mkswap /dev/sda2


swapon /dev/sda2


## 7 - mount /dev/sda1 /mnt
## 8 - pacstrap /mnt base linux linux-firmaware
## 9 - genfstab -U /mnt >> /mnt/etc/fstab


cat /mnt/etc/fstab


## 10 - arch-chroot /mnt
## 11 - ln -sf /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime
## 12 - hwclock --systohc
## 13 - uncomment in /etc/locale.gen


locale-gen


## 14 - echo LANG=en_US.UTF-8 > /etc/locale.conf
## 15 - echo KEYMAP=br-abnt2 > /etc/vconsole.conf
## 16 - echo arch > /etc/hostname
## 17 - in /etc/hosts


127.0.0.1   localhost
::1         localhost
127.0.0.1   arch.localdomain arch 


## 18 - passwd
## 19 - useradd -m -g users -G wheel robinson
## 20 - add robinson in /etc/sudoers


robinson ALL=(ALL) ALL


## 21 - pacman -S dosfstools os-prober mtools network-manager-applet networkmanager wpa_supplicant wireless_tools dialog sudo
## 22 - pacman -S grub


grub-install --target=i386-pc --recheck /dev/sda
mkdir /boot/grub/locale
cp /usr/share/locale/en@quot/LC_MESSAGES/grub.mo /boot/grub/locale/en.mo


## 23 - grub-mkconfig -o /boot/grub/grub.cfg
## 24 - remove disk
---------
## 25 - pacman -S xorg-server


for VIRTUALBOX
pacman -S virtualbox-guest-utils virtualbox-guest-modules-arch mesa mesa-libgl


## 26 - pacaman -S gnome gnome-extra
