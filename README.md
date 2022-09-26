# dotfiles

This Repo contains dotfiles configs

**ZSH Auto Configure**

[ZSH4HUMANS](https://github.com/romkatv/zsh4humans)

---

Install:

```
sudo pacman -S materia-gtk-theme

sudo pacman -S papirus-icon-theme

sudo pacman -S lxappearance
```

To configure displays:

run `arandr`

To check available storage:
install the follwing commands

`ncdu` , `duf` , `df`

---

Window Managers:

i3:

[Alacritty Begineers Guide](https://www.youtube.com/watch?v=76GbxnD8wnM&list=PLnur5_dvCveFGV8tKbH9sdqOSBUlFNQrR&index=18)

[rofi-emoji](https://github.com/Mange/rofi-emoji)

---

**For Brightness controller** keys:

My solution. It is tested on Ubuntu 20.04.

```
sudo apt install light

sudo chmod +s /usr/bin/light
```

Add to i3 config:

```
bindsym XF86MonBrightnessUp exec light -A 1 # increase screen brightness

bindsym XF86MonBrightnessDown exec light -U 1 # decrease screen brightness
```

---

**For ScreenShots:**

Flameshot is a decent alternative.

```
bindsym Print       exec flameshot full

bindsym Shift+Print exec flameshot gui
```

You can use option -p /path/to/directory to skip selecting the save directory.

---

NEOFETCH:

custom logo:

```
neofetch source ~/path-to-img-file
```

You can configure by commenting useless info by editing `~/.config/neofetch/config.conf` file

---

TREE:

to list out all files from current dir to sub dir install `tree`

```
sudo apt install tree -y
```

---

**for detailed list:**

```
sudo apt install colorls
#arch lnux
#sudo pacman -S colorls

#in you .bashrc or .zshrc, add the following line:
alias ls=colorls
```

**SSH PASSWORDLESS:**

```
sshpass "password" ssh user@ip
```

<!-- Switch to kali -->

### Resizing windows in i3 (without resize mode)

Found at [https://unix.stackexchange.com/questions/255344/resizing-windows-in-i3-without-resize-mode](https://unix.stackexchange.com/questions/255344/resizing-windows-in-i3-without-resize-mode)
Best solution:

Go to ~/.i3/config and open the file.

Paste following code at the end:

```
bindsym $mod+Ctrl+Right resize shrink width 1 px or 1 ppt
bindsym $mod+Ctrl+Up resize grow height 1 px or 1 ppt
bindsym $mod+Ctrl+Down resize shrink height 1 px or 1 ppt
bindsym $mod+Ctrl+Left resize grow width 1 px or 1 ppt
```

Save it and run `i3-msg` reload.

## Enable touchpad tap to click in i3

Found at [https://major.io/2021/07/18/tray-icons-in-i3/](https://major.io/2021/07/18/tray-icons-in-i3/)

> Solution:
> Let’s make it permanent in the i3 configuration. Open up ~/.config/i3/config and add a line:

`exec xinput set-prop "SynPS/2 Synaptics TouchPad" "libinput Tapping Enabled" 1`

> Via the xorg configuration method
> This method affects all window managers on your machine, so keep that in mind. Make a new file at /etc/X11/xorg.conf.d/touchpad-tap.conf and add the following:

```
Section "InputClass"
        Identifier "libinput touchpad catchall"
        MatchIsTouchpad "on"
        MatchDevicePath "/dev/input/event*"
        Driver "libinput"
        Option "Tapping" "on"
EndSection
```

We’re telling xorg to apply this configuration to any libinput touchpad on the system (but you could use the specific name of the device here if you want), and we’re enabling the tapping option.

You can make this change effective immediately with:

`xinput set-prop "SynPS/2 Synaptics TouchPad" "libinput Tapping Enabled" 1`

The xorg configuration change takes effect when you log out of your X session or you reboot your computer.
