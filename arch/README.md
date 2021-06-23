# Programs

To install my programs

```sudo pacman -S vim snapd arduino qcad blender kicad octave code cheese simplescreenrecorder gedit telegram-desktop filezilla gcc-fortran gource ghdl gtkwave anki mpv mplayer iverilog discord obs-studio lyx kdenlive qalculate-gtk kalgebra```

```sudo snap install spotify```

From AUR:
```whatsapp-nativefier wps-office typora minder-git```

[SimulIDE](https://www.simulide.com/)
[Digital](https://github.com/taffarel55/Digital/)

# Japanese Keyboard

First install these pkgs

```sudo pacman -S adobe-source-han-sans-jp-fonts otf-ipafont ibus ibus-anthy```

Then add to '~/.xprofile' this:
```
# Settings for Japanese input
export GTK_IM_MODULE='ibus'
export QT_IM_MODULE='ibus'
export XMODIFIERS=@im='ibus'

#Toolbar for anthy
ibus-daemon -drx
```

Restart the system and configure your keyboard with

```ibus-setup```

# KVM, QEMU and Virt Manager

1. To check hardware and kernel support

```LC_ALL=C lscpu | grep Virtualization```

```zgrep CONFIG_KVM /proc/config.gz```

2. Install KVM packages and install ebtables and iptables packages:

```sudo pacman -S qemu virt-manager virt-viewer dnsmasq vde2 bridge-utils openbsd-netcat ebtables iptables```

3. Enable and start service

```sudo systemctl enable libvirtd.service```

```sudo systemctl start libvirtd.service```

4. For network errors

```
sudo virsh net-list –all
sudo virsh net-autostart default
sudo virsh net-start default

```
# MATLAB

1. Install from 2 CD
2. Insert the license
3. Create the launcher and go to:

```~/.local/share/applications/matlab.desktop```

and edit this:
```
[Desktop Entry]
Version=1.1
Type=Application
Name=MATLAB 2018b
Comment=Matlabin
Icon=matlab
Exec=/usr/local/MATLAB/R2018b/bin/matlab
Actions=
Categories=Education;
Path=
Terminal=true
StartupNotify=false
```
4. Add this line ```export XAUTHORITY=/home/[user]/.Xauthority [app-name or path]``` to the ```/etc/profile```
5. Install [libselinux](https://aur.archlinux.org/packages/libselinux/)<sup>AUR</sup> and [libsepol](https://aur.archlinux.org/packages/libsepol/)<sup>AUR</sup>

# My scripts .bashrc

```
# My custom prompt
export PS1="\[\033[38;5;10m\]\u\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]\[\033[38;5;6m\]\W\[$(tput sgr0)\]\[\033[38;5;15m\] \\$ \[$(tput sgr0)\]"

openUSB() {
 sudo chmod 666 /dev/ttyACM0
 sudo chmod 666 /dev/ttyUSB0
}

up() {
 sudo pacman -Syu 
}

confScreen() {
 xrandr --newmode "1360x768_60.00"   84.75  1360 1432 1568 1776  768 771 781 798 -hsync +vsync
 xrandr --addmode eDP1 1360x768_60.00
 xrandr -s 1360x768_60.00
}

export HISTSIZE=10000
export HISTFILESIZE=10000

# End of my custom prompt
```
