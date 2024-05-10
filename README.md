# Arch linux gaming guide
This a personal guide I use to set up Arch for gaming on a fresh install.

## Step 1 - The Architect Script
This script will get you 80% there with setting up Arch for gaming. This script was oringally created by Cardiac13. Unfortunetly Cardiac13 terminated his account and passed on the Architect Script to A1RM4X. Just as a precaution and my laziness I forked the project just incase it gets deleted permentantly. I will use their script and linking so they get credit but if that disappears I have the fork on this repo.

Here is the Architect script that A1RM4X is currently maintaining [A1RM4X Architect Script](https://github.com/A1RM4X/Architect/blob/main/README-EN.md).

Again big thanks to **Cardiac13** for creating the script and **A1RM4X** for maintaining it.

### Disclaimer
> Using the Architect script may break something if using an Arch derivative like Endeavour OS. That derivative uses Dracut which I don't like. Down the road I will have a guide that won't need the Architect script. So for now use on Arch new installs **ONLY**.

install script
```
sudo pacman -S --needed git base-devel && git clone https://github.com/A1RM4X/Architect.git ~/Architect && cd ~/Architect && chmod +x ./architect.sh && ./architect.sh
```
Follow the questions based on your preference and hardware. One personal preference is to not use the Nvidia-ALL GPU driver for those with Nvidia GPU's. I just select no to it but it still installs the Nvidia propietary drivers.


## Step 2 - Optional Gaming Packages
This process is to install packages not covered in the Architect script, or I'm lazy to fix duplicates which there is a lot.


### Packages to install for gaming on Arch
```
sudo pacman -S --needed wine giflib lib32-giflib libpng lib32-libpng libldap lib32-libldap gnutls lib32-gnutls mpg123 \ lib32-mpg123 openal lib32-openal v4l-utils lib32-v4l-utils libpulse lib32-libpulse libgpg-error lib32-libgpg-error \ alsa-plugins lib32-alsa-plugins alsa-lib lib32-alsa-lib libjpeg-turbo lib32-libjpeg-turbo sqlite lib32-sqlite \ libxcomposite lib32-libxcomposite libxinerama lib32-libgcrypt libgcrypt lib32-libxinerama ncurses lib32-ncurses \ ocl-icd lib32-ocl-icd libxslt lib32-libxslt libva lib32-libva gtk3 lib32-gtk3 gst-plugins-base-libs \ lib32-gst-plugins-base-libs vulkan-icd-loader lib32-vulkan-icd-loader bottles cups dosbox glfw lib32-opencl-icd-loader lib32-vkd3d \ lutris opencl-icd-loader samba steam steam-native-runtime vkd3d wine-gecko  winetricks gamescope goverlay \ mangohud lib32-mangohud ttf-liberation lib32-fontconfig wqy-zenhei
```

The idea for which packages to include came from the following sources...

- CachyOS Meta Package
- Arch AUR Meta Package
- [Lutris](https://github.com/lutris/docs/blob/master/WineDependencies.md)

## Step 3 - The Kernel
Each computer has its own preference, however for my PC both the CachyOS EEDEV and TKG EEDEV work perfect.

Depending on the Kernel your more familar with, install the CachyOS Kernel from the AUR or the TKG Kernel from the [Frogging Family Github](https://github.com/Frogging-Family/linux-tkg)

## Step 4 - Customizing Steam for Speed and Performance
This section will configure Steam for download speed and help select environmental variables.

### Step A - Enhance the download speed
#### Create/Edit `.steam/steam/steam_dev.cfg`
```bash
nano ~/.steam/steam/steam_dev.cfg 
```
Inside the file paste the following...
```bash
@nClientDownloadEnableHTTP2PlatformLinux 0
@fDownloadRateImprovementToAddAnotherConnection 1.0
```
### Step B - Set up your game with Proton-GE
Use Proton Up to get the latest Proton-GE version needed for playing Windows games on Arch

From the `Steam Library` right click your game and select `properties`. Under `Compatibility` place a check on Force the use of a specific Steam Play compatibility tool and select the Proton GE version you downloaded from Proton-Up.

### Step C - Steam Environmental Variables
While still in your game properties select `General`. Under launch options for basic variables such as Gamemode and Mangohud use the following...
```
gamemoderun MANGOHUD=1 %command%
```
That's it your basically done, you should be able to click Play on your game and launch it. One protip if your experiencing issues, launch Steam via the terminal, which will help you find the error as everything the app does is printed out.
