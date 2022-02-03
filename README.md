# dotfiles
This Repo contains dotfiles configs

**ZSH Auto Configure**

[ZSH4HUMANS](https://github.com/romkatv/zsh4humans)


-----

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

------

Window Managers:

i3:


[Alacritty Begineers Guide](https://www.youtube.com/watch?v=76GbxnD8wnM&list=PLnur5_dvCveFGV8tKbH9sdqOSBUlFNQrR&index=18)


[rofi-emoji](https://github.com/Mange/rofi-emoji)

------
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
------

**For ScreenShots:**

Flameshot is a decent alternative.

```
bindsym Print       exec flameshot full

bindsym Shift+Print exec flameshot gui
```

You can use option -p /path/to/directory to skip selecting the save directory.

-----


NEOFETCH:

custom logo:

```
neofetch source ~/path-to-img-file
```

You can configure by commenting useless info by editing `~/.config/neofetch/config.conf` file

-----

TREE:

to list out all files from current dir to sub dir install `tree`

```
sudo apt install tree -y
```

-----


**for detailed list:**

```
sudo apt install colorls
#arch lnux
#sudo pacman -S colorls

#in you .bashrc or .zshrc, add the following line:
alias ls=colorls
```
