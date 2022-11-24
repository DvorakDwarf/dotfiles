# dotfiles
My dotfiles on arch linux. WIP

<h1 align="center"><i><u>~/dotfiles</u></i></h1>

# Information
Here are some details about my setup:
- OS: [Arch Linux](https://archlinux.org/)
- Terminal: [Wezterm](https://github.com/wez/wezterm)
- Shell: [Bash](https://www.gnu.org/software/bash/)
- WM: [dwm-flexipatch](https://github.com/bakkeby/dwm-flexipatch)
- Login Manager: [ly](https://github.com/fairyglade/ly)
- Editor: [nvim](https://github.com/neovim/neovim)
---
- Status Bar: vanilla dwm bar
- Status Content: [luastatus](https://github.com/shdown/luastatus)
- Lock Screen: [slock-flexipatch](https://github.com/bakkeby/slock-flexipatch)
- App Menu: [rofi](https://github.com/davatorium/rofi)
- Network Menu: [networkmanager-dmenu](https://github.com/firecat53/networkmanager-dmenu)
- Dropdown Menu: [tdrop](https://github.com/noctuid/tdrop)
- Notification Daemon: [Linux Notification Center](https://github.com/phuhl/linux_notification_center)
- AUR helper: [Paru](https://github.com/Morganamilo/paru)
- Power Management: [Xfce Power Manger](https://docs.xfce.org/xfce/xfce4-power-manager/start)
- Brightness Control: [brightnessctl](https://github.com/Hummer12007/brightnessctl)
- Compositor: [picom](https://github.com/yshui/picom)
---
- Font: [Iosevka Nerd Font](https://www.nerdfonts.com/)
- Shell Prompt: [starship](https://github.com/starship/starship)
- System Info: [macchina](https://github.com/Macchina-CLI/macchina)
---
- File Manager: [nnn](https://github.com/jarun/nnn) and [Thunar](https://docs.xfce.org/xfce/thunar/start)
- Ebook Reader: [zathura](https://github.com/pwmt/zathura)
- Image Viewer: [qView](https://github.com/jurplel/qView)
- Video Player: [mpv](https://github.com/mpv-player/mpv)
- ScreenShot: [Flameshot](https://github.com/flameshot-org/flameshot)
- Wallpaper Setter: [feh](https://github.com/derf/feh)
- Color Picker: [Gpick](https://github.com/thezbyg/gpick)
- Clipboard Manager: [greenclip](https://github.com/erebe/greenclip)
- Calculator: [rofi-calc](https://github.com/svenstaro/rofi-calc)

# Setup 

<details>
<summary><b>Arch Linux or Arch based distro</b></summary>

### Mandatory Steps

> __WARNING!!! Backup your dotfiles from your home directory. These steps below will overwrite your configs.__

- Clone this repo to your preferred directory and cd into it - ```git clone https://github.com/junnunkarim/dotfiles-linux && cd dotfiles-linux```

- Install mandatory dependencies
	- ```sudo pacman -Su --needed base-devel coreutils xorg wezterm lua feh ttf-iosevka-nerd ttc-iosevka wmctrl```
	- Install luastatus
		- ```sudo pacman -Su --needed cmake yajl python-docutils```
		- Continue from here - [luastatus](https://github.com/shdown/luastatus#installation)
- Copy necessary configs -
	- ```cp -rf .bin .Xresources .xinitrc ~```
    - If you won't use my bashrc then add ```.bin``` to your $PATH variable
    - __Do not copy ```.xsession``` as it will change your keyboard layout to dvorak.__
	- ```cp -rf .config/wezterm .config/dwm .config/rofi .config/wallpaper ~/.config/```
- Build dwm and dmenu
	- ```cd ~/.config/dwm && sudo make install```
	- ```cd ~/.config/dmenu && sudo make install```
- Create a desktop entry for dwm
	- ```sudo vim /usr/share/xsessions/dwm.desktop```
	```
	[Desktop Entry]
	Encoding=UTF-8
	Name=dwm
	Comment=the dynamic window manager
	Exec=dwm
	Icon=dwm
	Type=XSession
	```
- Open ```$HOME/.config/dwm/config.h``` in a text editor and modify the keybindings to your needs
- Extract the gtk themes from ```.themes``` directory to your ```$HOME/.themes``` directory
- Login to dwm using a display manager
	- After getting into dwm press ```super + t``` and choose any colorscheme (this is to load the wallpaper for the first time)

### Optional steps

> __For each options below, make sure that you are in the dotfiles-linux directory__

- Install paru (AUR helper)
	- ```git clone https://aur.archlinux.org/paru.git```
	- ```cd paru```
	- ```makepkg -si```
- If you want to use my ```.bashrc```
	- ```cp .bashrc ~```
	- ```sudo pacman -Su --needed exa starship```
	- ```paru -S --needed macchina```
- nvim dotfiles
  - ```cp -rf .config/nvim ~/.config```
- If you want to use my ```.vimrc``` 
	- ```cp .vimrc ~```
	- install [vim-plug](https://github.com/junegunn/vim-plug)
	- setup [coc-nvim](https://github.com/neoclide/coc.nvim)
- brightnessctl
	- ```sudo pacman -Su --needed brightnessctl```
- picom
	- ```sudo pacman -Su --needed picom```
- networkmanager-dmenu
	- ```paru -S --needed networkmanager-dmenu-git```
- redshift
	- ```sudo pacman -Su --needed redshift```
- Dropdown terminal
	- ```paru -S --needed alacritty tdrop tmux```
	- ```cp -rf .config/alacritty ~/.config```
- zathura
	- ```sudo pacman -Su --needed zathura```
	- ```cp -rf .config/zathura ~/.config/```
- slock
	- ```cp -rf .config/slock ~/.config/```
	- ```cd ~/.config/slock && sudo make install```
	- Continue lockscreen setup using [arch wiki - slock](https://wiki.archlinux.org/title/Slock)

</details>

# Default Keybindings
> __Standards__ <br>
> super + [any key] == system main shortcuts <br>
> super + shift + [any key] == system main shortcuts <br>
> super + ctrl + shift + [any key] == system low priority shortcuts <br>
> super + alt + shift + [any key] == system low priority shortcuts <br>
> alt + [any num or alphabet key] == open applications  <br>
> ctrl + [any num or alpabet key] == open other programs or scripts <br>

<details>
<summary><b>Keybindings</b></summary>

| __Keybinding__								| __Action__ |
| --- 													| --- |
| super + b											| toggle bar on/off |
| super + s											| switch a window form stack with master |
| super + c											| close a program	|
| super + shift + q							| quit dwm (only if all programs are closed) |
| super + space									| toggle floating on/off |
| super + left/right						| increase/decrease window size |
| super + shift + ctrl + space 	| cycle through all layouts |
| super + tab										| move through active tags clockwise |
| super + backtick							| move through active tags anti-clockwise |
| super + 0 (zero)							| toggle gaps on/of |
| super + shift + i							| hide/unhide window |
| super + shift + r							| restart dwm |
| super + f											| toggle fullscreen |
| super + 0-9										| go to the specified tag |
| super + shift + 0-9						| move selected window to the specified tag |
| alt + tab											| move through window focus clockwise |
| alt + backtick								| move through window focus anti-clockwise |

| __Keybinding__								| __Action__ |
| ---														| --- |
| super + return/enter					| open terminal |
| super + shift + return/enter	| open dropdown terminal |
| super + l											| lock screen |
| super + n											| open network menu |
| super + t											| open theme switcher |
| super + x											| open powermenu |
| super + k											| show all keybindings |
| super + d											| open rofi |
| super + h											| open clipboad manager (greenclip) |
| super + r											| open calculator (rofi-calc) |
| super + ctrl + r							| turn on bluelight filter (redshift) |
| super + ctrl + n							| turn off bluelight filter (redshift) |
| super + ctrl + p              | turn on compositor (picom) |
| super + ctrl + u              | turn on compositor (picom) |
| super + ctrl + g							| open color picker (gpick) |
| super + alt + f								| open file manager (thunar) |
| super + alt + n								| open file manager (nnn) |
| super + alt + b								| open chromium |
| super + alt + e								| open firefox |
| super + alt + e								| open neovim |
| super + alt + h								| open btop |
| prtsc													| take fullscreen screenshot now |
| super + prtsc									| take interective screenshot |
| alt + prtsc										| take fullscreen screenshot after 5 sec |
| ctrl + prtsc									| take fullscreen screenshot after 10 sec |
| super + F1										| increase brightness |
| super + F2										| decrease brightness |
| super + F5										| increase volume |
| super + F6										| decrease volume |
| super + F7										| toggle mute on/off |

</details>

# Screenshots

<details>
<summary><b>click here</b></summary>

WIP

</details>

# Credit
- https://github.com/junnunkarim/dotfiles-linux#readme for the readme reference
