<h1 align="center"><i><u>Mah' Dotfiles</u></i></h1>

# Information
Details:
- OS: [Arch Linux](https://archlinux.org/)
- Terminal: [Alacritty](https://github.com/alacritty/alacritty)
- Shell: [Oh-My-Zsh](https://ohmyz.sh/)
- WM: [i3](https://i3wm.org/)
- Editor: [VScode](https://github.com/microsoft/vscode)
---
- Status Bar: [Polybar](https://github.com/polybar/polybar)
- App Menu: [Rofi](https://github.com/davatorium/rofi)
- Notification Daemon: [Dunst](https://github.com/dunst-project/dunst)
- AUR helper: [Paru](https://github.com/Morganamilo/paru)
- Compositor: [Picom](https://github.com/yshui/picom)
---
- Font: [Iosevka Nerd Font](https://www.nerdfonts.com/)
- System Info: [Neofetch](https://github.com/dylanaraps/neofetch)
- Desktop System Manager: [Conky](https://github.com/brndnmtthws/conky)
---
- Browser: [Firefox](https://github.com/mozilla/)
- File Manager: [Thunar](https://docs.xfce.org/xfce/thunar/start)
- Ebook Reader: [Zathura](https://github.com/pwmt/zathura)
- Image Viewer: [Feh](https://github.com/derf/feh)
- Video Player: [MPV](https://github.com/mpv-player/mpv)
- ScreenShot: [Flameshot](https://github.com/flameshot-org/flameshot)

# Setup 

<details>
<summary><b>Arch Linux or Arch based distro</b></summary>

### Mandatory Steps

> __WARNING!!! Always backup your dotfiles from your home directory.__

- Clone this repo to your preferred directory and cd into it - ```git clone https://github.com/DvorakDwarf/dotfiles.git```

- Install all the pacman stuff
	- ```sudo pacman -S base-devel coreutils xorg feh ttf-iosevka-nerd i3 xorg-xinit zsh lxappearance flameshot polybar rofi dunst picom mpv thunar thunar-archive-plugin conky feh```
- Install my recommended programs
	- ```sudo pacman -S neofetch zathura firefox qview discord steam vtop```
- Install paru (AUR helper)
	- ```git clone https://aur.archlinux.org/paru.git```
	- ```cd paru```
	- ```makepkg -si```
- Install AUR packages
	- ```paru -S zscroll-git betterdiscordctl visual-studio-code-bin graphite-gtk-theme oh-my-zsh-git ```
- Install zsh plugins
	-```git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions``` 
	-```git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting```
- Change shell to zsh 
	-```sudo chsh $USER -s /bin/zsh```
- Copy necessary configs from the repo
- Install BetterDiscord
	- betterdiscordctl install
	- For themes, install ```Dark+, Float, and Discord 11```
	- For the green look, edit Dark+ and change the colors to:
	![2022-11-18_09-12_1](https://user-images.githubusercontent.com/96934612/203893338-76bcff8f-74cd-4cc3-b4d0-76cb80097f6b.jpg)
- Install spicetify
	- Install the marketplace
	- The theme I used was ```onepunch```
- Open ```$HOME/.config/i3/config``` in a text editor and modify the keybindings to your needs
- use lxappearence to set the theme. I use Graphite-green-dark. It should have been installed on the AUR stage
- vscode theme I use is [Gruvbox-ish](https://marketplace.visualstudio.com/items?itemName=GracefulPotato.gruvbox-ish)
- DM me on discord if you are having issues
</details>
	
# Screenshots

<details>
<summary><b>click here</b></summary>

![2022-10-27_19-21](https://user-images.githubusercontent.com/96934612/203892835-8a63a7b7-8534-4aaf-8f1e-6ad869b593e2.jpg)
	
![2022-11-17_15-30](https://user-images.githubusercontent.com/96934612/203892838-1f7e51eb-598a-4874-b18b-5314a48c248f.jpg)


</details>

# Credit
- https://github.com/junnunkarim/dotfiles-linux#readme for the readme reference
- r/unixporn for getting me into linux
