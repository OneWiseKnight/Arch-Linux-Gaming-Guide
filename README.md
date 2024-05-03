# Arch linux gaming guide

Basic suggestions to enhance gaming performance. For Arch new installs **ONLY** its highly recommended you just go with this script which will get you 90% there.

### Disclaimer
This guide should primarly be used on a fresh install of Arch Linux. Using the Architect script may break something for example in Endeavour OS which uses Dracut. Down the road I will have a guide that won't need the Architect script.

Big Thanks to Cardiac13 for creating the Architect Script. Unfortunetly Cardiac terminated his account and passed on the Architect Script to A1RM4X. Just as a precaution and my laziness I forked the project just incase it gets deleted permentantly. I will use their script and linking so they get credit but if that disappears I have the fork on this repo.

Here is the Architect script that A1RM4X is currently maintaining [Gaming-Linux-FR Architect Script](https://github.com/A1RM4X/Architect/blob/main/README-EN.md).


## Linux distribution



## Packages to install for gaming on Arch and derivatives

```
sudo pacman -S --needed wine giflib lib32-giflib libpng lib32-libpng libldap lib32-libldap gnutls lib32-gnutls mpg123 \ lib32-mpg123 openal lib32-openal v4l-utils lib32-v4l-utils libpulse lib32-libpulse libgpg-error lib32-libgpg-error \ alsa-plugins lib32-alsa-plugins alsa-lib lib32-alsa-lib libjpeg-turbo lib32-libjpeg-turbo sqlite lib32-sqlite \ libxcomposite lib32-libxcomposite libxinerama lib32-libgcrypt libgcrypt lib32-libxinerama ncurses lib32-ncurses \ ocl-icd lib32-ocl-icd libxslt lib32-libxslt libva lib32-libva gtk3 lib32-gtk3 gst-plugins-base-libs \ lib32-gst-plugins-base-libs vulkan-icd-loader lib32-vulkan-icd-loader bottles cups dosbox glfw lib32-opencl-icd-loader lib32-vkd3d \ lutris opencl-icd-loader samba steam steam-native-runtime vkd3d wine-gecko wine-mono winetricks gamescope goverlay \ proton-cachyos mangohud lib32-mangohud ttf-liberation lib32-fontconfig wqy-zenhei
```

If your looking for some more packages to install Lutris has a good document [Lutris](https://github.com/lutris/docs/blob/master/WineDependencies.md)




install Architect
- This will take care of essential drivers, hooks, vmlimits, and introductory software

install Kernel CachyOS or TKG

install CachyOS Gaming Meta or the following packages...

Use Proton Up to get the latest Proton-GE version needed for playing Windows games on Arch

customizing Steam 
1) Increase the buffers config file

Create/Edit **/.steam/steam/steam_dev.cfg**
```
nano ~/.steam/steam/steam_dev.cfg 
```
Inside the file paste the following...
```
@nClientDownloadEnableHTTP2PlatformLinux 0
@fDownloadRateImprovementToAddAnotherConnection 1.0
```

2) Set up your game with Proton
3) Recommended Environmental Variables Gamemode Mangohud etc...


















### Increase ulimit -Hn

Increase limit to **DefaultLimitNOFILE=1048576**
```
sudo nano /etc/systemd/system.conf
```

Increase limit to **DefaultLimitNOFILE=1024:1048576**
```
sudo nano /etc/systemd/user.conf
```
