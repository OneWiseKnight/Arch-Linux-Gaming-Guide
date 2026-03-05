# Arch linux gaming guide
This a personal guide I use to set up Arch for gaming on a fresh install.

## Step 1 - The Gaming Packages

### Option A - Cachyos/Cachyos Repo is Installed
> [!NOTE]
> If you have Cachyos installed or using the Cachyos Repo, then use the Cachyos Meta Package.

Open your terminal and use the following command.
```
sudo pacman -S cachyos-gaming-meta
```
### Option B - Manual Individual Package
This option is for those that don't want to use the Cachyos Meta Package.

> [!CAUTION]
> Only use the bottom command if you are __not__ on Cachyos, or, not planning to install any gaming meta package.
> Highly recommended to use the Meta package from Cachyos.

```
sudo pacman -S --needed wine giflib lib32-giflib libpng lib32-libpng libldap lib32-libldap gnutls lib32-gnutls mpg123 \ lib32-mpg123 openal lib32-openal v4l-utils lib32-v4l-utils libpulse lib32-libpulse libgpg-error lib32-libgpg-error \ alsa-plugins lib32-alsa-plugins alsa-lib lib32-alsa-lib libjpeg-turbo lib32-libjpeg-turbo sqlite lib32-sqlite \ libxcomposite lib32-libxcomposite libxinerama lib32-libgcrypt libgcrypt lib32-libxinerama ncurses lib32-ncurses \ ocl-icd lib32-ocl-icd libxslt lib32-libxslt libva lib32-libva gtk3 lib32-gtk3 gst-plugins-base-libs \ lib32-gst-plugins-base-libs vulkan-icd-loader lib32-vulkan-icd-loader bottles cups dosbox glfw lib32-opencl-icd-loader lib32-vkd3d \ lutris opencl-icd-loader samba steam steam-native-runtime vkd3d wine-gecko  winetricks gamescope goverlay \ mangohud lib32-mangohud ttf-liberation lib32-fontconfig wqy-zenhei
```

### Option C - The Architect Script
This script will get you 80% there with setting up Arch for gaming.
> [!CAUTION]
> Again only use this script if you do not have Cachyos installed or the Cachyos Repo, and using Arch. 

Here is the link to the Architect script [Cardiacman13 Architect Script](https://github.com/Cardiacman13/Architect).
Again big thanks to **Cardiac13** for creating the script.

> [!NOTE]
> The Architect script is intended for clean installs of Arch. In the same vein using the script in a derivative may break something. Rather than take a risk check on the Architect Script's author website for more information.

## Step 2 - Optional Gaming Packages
Install the software of choice, whether it is Steam, Lutris, or Bottles.



The idea for which packages to include came from the following sources...

## Step 3 - The Kernel
Each computer has its own preference, however for my PC both the CachyOS Linux and TKG PDS kernels have the highest performance.

Depending on the Kernel your more familar with, install the CachyOS Kernel from the Cachyos Repo, Compile it, or get the TKG Kernel from the [Frogging Family Github](https://github.com/Frogging-Family/linux-tkg)

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
> [!TIP]
> Instead of Feral Gamemode, game-performance by Cachyos is very powerful and yields better performance in my testing.

That's it your basically done, you should be able to click Play on your game and launch it. One protip if your experiencing issues, launch Steam via the terminal, which will help you find the error as everything the app does is printed out.
