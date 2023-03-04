!#/bin/bash

# applications and services for initial setup
# for updating initial linux distro

sudo pacman -Syyu -y


#installing text editors

sudo pacman -S vim
sudo pacman -S vi
sudo pacman -S nano
sudo pacman -S touch


#installing amd drivers

sudo pacman -S xf86-video-amdgpu vulkan-radeon libva-mesa-driver mesa-vdpau


#remove nvidia drivers

pacman -Rdn nvidia nvidia-utils


#

# virtualbox install


sudo pacman -S linux-headers

sudo pacman -S virtualbox virtualbox-guest-iso

sudo pacman -S net-tools

sudo modprobe vboxdrv

yay -S virtualbox-ext-oracle



# vmware install

sudo pacman -S fuse2 gtkmm linux-headers pcsclite libcanberra

yay -S --noconfirm --needed ncurses5-compat-libs

yay -S --noconfirm --needed  vmware-workstation

sudo systemctl enable vmware-networks.service vmware-usbarbitrator.service vmware-hostd.service

sudo systemctl start vmware-networks.service vmware-usbarbitrator.service vmware-hostd.service

sudo systemctl enable vmware-hostd.service vmware-hostd.service vmware-hostd.service

sudo systemctl start vmware-hostd.service vmware-hostd.service vmware-hostd.service

sudo modprobe -a vmw_vmci vmmon



# vmware tools

sudo pacman -S open-vm-tools

sudo systemctl enable --now vmtoolsd


# nmap install

sudo pacman -S nmap


# installing discord

sudo pacman -S discord


# download flameshot

pacman --sync flameshot

chmod +x Flameshot-*.x86_64.AppImage

./Flameshot-*.x86_64.AppImage


# install libre applications

sudo pacman -S --needed ttf-caladea ttf-carlito ttf-dejavu ttf-liberation ttf-linux-libertine-g noto-fonts adobe-source-code-pro-fonts adobe-source-sans-pro-fonts adobe-source-serif-pro-fonts

paru ttf-gentium-basic

paru hsqldb2-java

sudo pacman -S --needed jre-openjdk

sudo pacman -S libreoffice-still

sudo pacman -S hunspell

sudo pacman -S hunspell-en_us

paru libreoffice-extension-languagetool

#source - https://discovery.endeavouros.com/gaming/steam-lutris-wine/2022/01/
#installing steam

sudo pacman -S steam

yay -S game-devices-udev


#installing lutris

sudo pacman -S lutris


#installing wine

sudo pacman -Sy wine


#Some basic KDE packages including Calculator, Camera app, Emoji fonts (If KDE Emoji picker app shows blocks), Firewall & Bluetooth

sudo pacman -S noto-fonts-emoji xdg-desktop-portal xdg-desktop-portal-kde plasma-systemmonitor plasma-browser-integration kcharselect kamoso krename kdeplasma-addons plasma-firewall bluedevil kcalc

#System profile enabling

sudo pacman -S power-profiles-daemon

sudo systemctl enable power-profiles-daemon.service

sudo systemctl start power-profiles-daemon.service


#bluetooth enable

sudo pacman -S bluez-utils bluedevil

sudo rfkill unblock bluetooth

sudo systemctl enable bluetooth


#trim SSD sectors

sudo systemctl enable fstrim.timer

sudo systemctl start fstrim.timer


#install firewall

sudo pacman -S ufw plasma-firewall

sudo systemctl enable --now ufw.service

sudo ufw enable

sudo systemctl enable ufw


#disable baloo file indexer

balooctl suspend

balooctl disable


#removes unwanted dependencies

yay -Yc


#remove uninstall package cache

sudo pacman -Sc


#remove whole package directory

sudo pacman -Scc


#remove cahce dir in home dir

rm -rf .cache/*


#removes orphan packages

sudo pacman -Rns $(pacman -Qdtq)



#updating os and database after install

yay -Syyu
sudo pacman -Syyu -y

#backup device feature with timeshift

sudo pacman -S grub-btrfs

yay -S timeshift

yay -S timeshift-autosnap

sudo grub-mkconfig -o /boot/grub/grub.cfg
