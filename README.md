# Raspberry Pi Ubuntu 20.04 aarch64 Desktop
[![Discord](https://img.shields.io/discord/316245914987528193?logo=discord)](https://discord.com/invite/v8dAnFV) [![Youtube](https://img.shields.io/badge/YouTube-FF0000?style=flat-square&logo=youtube&logoColor=white)](https://www.youtube.com/channel/UCrjKdwxaQMSV_NDywgKXVmw) [![Twitter URL](https://img.shields.io/twitter/follow/novaspirittech?style=flat-square&logo=twitter)](https://twitter.com/novaspirittech)


[![](https://github.com/novaspirit/rpi_ubu64_desktop/raw/main/screenshot.png)](https://github.com/novaspirit/rpi_ubu64_desktop/blob/main/screenshot.png)

This is a write up of novaspirit rpi4 ubuntu desktop video [here](https://youtube.com/novaspirittech/)

In this write up I will provide links used in the video as reference, please refer to the video for how everything is setup.

Setting up ubuntu to run on ssd
https://www.raspberrypi.org/forums/viewtopic.php?t=278791

### gnome
```sh
sudo apt install ubuntu-gnome-desktop ubuntu-gnome-default-settings
```

### gnome extensions

```sh
sudo apt install chrome-gnome-shell gnome-tweak-tool
```

### ubuntu software center
```sh
sudo apt install gnome-software 
sudo apt install snapd
sudo apt install flatpak
sudo apt install gnome-software-plugin-flatpak gnome-software-plugin-snap
```

### preload (optional)
```sh
apt install preload
```

### box86 install
you can install via source which i would recommend
[https://github.com/ptitSeb/box86](https://github.com/ptitSeb/box86)
or download the compile and packaged DEB from my discord 
[https://discord.gg/v8dAnFV](https://discord.gg/v8dAnFV)

```sh
sudo dpkg --add-architecture armhf
```
```sh
sudo apt install libc6:armhf  libx11-6:armhf  libgdk-pixbuf2.0-0:armhf libgtk2.0-0:armhf libstdc++6:armhf libsdl2-2.0-0:armhf mesa-va-drivers:armhf libsdl1.2-dev:armhf libsdl-mixer1.2:armhf libpng16-16:armhf libcal3d12v5:armhf libsdl2-net-2.0-0:armhf libopenal1:armhf libsdl2-image-2.0-0:armhf libvorbis-dev:armhf libcurl4:armhf osspd:armhf pulseaudio:armhf libjpeg62:armhf libudev1:armhf libgl1-mesa-dev:armhf libsnappy1v5:armhf libx11-dev:armhf libsmpeg0:armhf libboost-filesystem1.67.0:armhf libboost-program-options1.67.0:armhf libavcodec58:armhf libavformat58:armhf libswscale5:armhf libmyguiengine3debian1v5:armhf libboost-iostreams1.67.0:armhf  libsdl2-mixer-2.0-0:armhf
```

this is needed for ubuntu 20.10

```sh
sudo apt install libc6:armhf  libx11-6:armhf  libgdk-pixbuf2.0-0:armhf libgtk2.0-0:armhf libstdc++6:armhf libsdl2-2.0-0:armhf mesa-va-drivers:armhf libsdl1.2-dev:armhf libsdl-mixer1.2:armhf libpng16-16:armhf libcal3d12v5:armhf libsdl2-net-2.0-0:armhf libopenal1:armhf libsdl2-image-2.0-0:armhf libvorbis-dev:armhf libcurl4:armhf osspd:armhf pulseaudio:armhf libjpeg62:armhf libudev1:armhf libgl1-mesa-dev:armhf libsnappy1v5:armhf libx11-dev:armhf libsmpeg0:armhf libboost-filesystem1.71.0:armhf libboost-program-options1.71.0:armhf libavcodec58:armhf libavformat58:armhf libswscale5:armhf libmyguiengine3debian1v5:armhf libboost-iostreams1.71.0:armhf  libsdl2-mixer-2.0-0:armhf
```


### zoom
```sh
sudo apt install libxcb-shape0:armhf libxcb-randr0:armhf libxcb-image:armhf libxcb-image0:armhf libxcb-xtest0:armhf libxcb-keysyms1:armhf libdbus-1-3:armhf
```

### steam
```sh
wget https://steamcdn-a.akamaihd.net/client/installer/steam.deb
```
```sh
sudo apt install libnss3:armhf libnm0:armhf libdbus-glib-1-2:armhf libudev1:armhf libnspr4:armhf libgudev-1.0-0:armhf libusb-1.0-0:armhf libappindicator1:armhf
```
> add this for more box86 diag
>``` BOX86_DLSYM_ERROR=1 ```

```sh
STEAMOS=1 STEAM_RUNTIME=1 steam
```

### Extensions Gnome
gnome extenstions I used
| extension | URL |
| --------- | --- |
| blur my shell | https://extensions.gnome.org/extension/3193/blur-my-shell/ |
| dash to panel | https://extensions.gnome.org/extension/1160/dash-to-panel/ |
| user themes | https://extensions.gnome.org/extension/19/user-themes/ |
| compiz alike window (wobbly) | https://extensions.gnome.org/extension/3210/compiz-windows-effect/ |
| cpufreq(konkor) | https://extensions.gnome.org/extension/1082/cpufreq/ |
| Tray Icons | https://extensions.gnome.org/extension/1503/tray-icons/ |
| TopHat | https://extensions.gnome.org/extension/5219/tophat/ |
| Clipboard Indicator | https://extensions.gnome.org/extension/779/clipboard-indicator/ |
| Coverflow Alt-Tab | https://extensions.gnome.org/extension/97/coverflow-alt-tab/ |
| Desktop Cube | https://extensions.gnome.org/extension/4648/desktop-cube/ |
| Rounded Window Corners | https://extensions.gnome.org/extension/5237/rounded-window-corners/ |
| Rounded Corners | https://extensions.gnome.org/extension/1514/rounded-corners/ |
| GSconnect | https://extensions.gnome.org/extension/1319/gsconnect/ |

### Programs
olive
astromenece (flatpak)
flameshot
krita
vscode (http://code.headmelted.com/)


### winetricks
this is needed to avoid adobeair error
```sh
sudo sed -i 's|echo "\${arg%%=\*}"=\\""${arg### \*=}"\\"|echo \${arg%%=\*}=\\"\${arg### \*=}\\"|g' /usr/local/bin/winetricks
sudo apt install cabextract libncurses5:armhf
```

### wine
wine 5.11

### Deskpi
needed for deskpi fan controller
https://github.com/DeskPi-Team/deskpi

### extra
this will remove the frequently used program from gnome shell
```sh
gsettings set org.gnome.desktop.privacy remember-app-usage false
```


