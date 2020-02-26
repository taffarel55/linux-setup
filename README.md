# Codigos escritos por mim
```
export PS1="\[\033[38;5;10m\]\u\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]\[\033[38;5;6m\]\W\[$(tput sgr0)\]\[\033[38;5;15m\] \\$ \[$(tput sgr0)\]"

abrirPorta() {
 sudo chmod 666 /dev/ttyACM0
}

up() {
 sudo pacman -Syu 
}

confScreen() {
 xrandr --newmode "1360x768_60.00"   84.75  1360 1432 1568 1776  768 771 781 798 -hsync +vsync
 xrandr --addmode eDP1 1360x768_60.00
 xrandr -s 1360x768_60.00
}

```
