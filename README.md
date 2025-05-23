# Не большая переделка дотфайлов сапога с Monet

![Скрин 1](/docs/screen1.jpg)

![Скрин 2](/docs/screen2.jpg)

![Скрин 3](/docs/screen3.jpg)
## Что используется
| Для чего      | Утилита          |
| ------------- | ---------------- |
| WM            | Hyprland         |
| OS            | Arch Linux       |
| Terminal      | Alacritty        |
| File Manager  | Nautilus         |
| Fetch         | FastFetch        |
| Shell         | Fish             |
| Text Editor   | Emacs            |
| Launcher      | Rofi             |
| Bar           | Waybar           |
| Theme picker  | Pywal            |
| Notifications | Mako             | 

## Пока что не советую использовать это, не все еще готово.

## Автоматическая установка
```sh
$ sudo pacman -Syy --needed git base-devel && git clone https://github.com/Spbog/dotfiles.git && cd dotfiles && ./install.sh
```

## Ручная установка
Установите _git_ и _base-devel_:
```sh
$ sudo pacman -Syy --needed git base-devel
```
Скопируйте дотфайлы и перейдите в директорию с ними:
```sh
$ git clone https://github.com/Spbog/dotfiles.git && cd dotfiles/
```
Установите _yay_ (если вы ещё это не сделали):
```sh
$ git clone https://aur.archlinux.org/yay.git && cd yay/ && makepkg -si && cd .. && rm -rf yay/
```
Установите зависимости:
```sh
$ sudo pacman -R --noconfirm pulseaudio
$ yay -S --noconfirm hyprland rofi-wayland waybar hyprlock walogram-git pywal python3 python-pip python-pywalfox swww grim slurp mako emacs nautilus pipewire pipewire-pulse wireplumber pavucontrol helvum alacritty zoxide thefuck oh-my-posh wl-clipboard noto-fonts-emoji brightnessctl fastfetch fish fisher-git playerctl nm-connection-editor
$ pip3 install colorz --user --break-system-packages
```
Поменяйте шелл:
```sh
$ chsh -s /usr/bin/fish
```
Измените и скопируйте аватар профиля _avatar.png_
```sh
$ cp avatar.png ~/avatar.png
```
Переместите файлы из _config/_ в _~/.config/_, а _fonts/_ в _~/.local/share/fonts/_. 
```sh
$ cp -r config/* ~/.config && cp -r fonts ~/.local/share/fonts/
```
Скопируйте папку с обоями _"Wallpapers"_ в _~/Wallpapers_. Скопируйте туда любые обои.
```sh
$ cp -r Wallpapers ~/Wallpapers
```
Создайте тему из обоев:
```sh
$ wal -i ~/Wallpapers/file --saturate 0.2 --backend colorz
```
После сделайте симлинки на файлы из _.cache_ в _.config_:
```sh
$ ln -sf ~/.cache/wal/colors-waybar.css ~/.config/waybar/colors-waybar.css
$ ln -sf ~/.cache/wal/hyprlock.conf ~/.config/hypr/hyprlock.conf
$ ln -sf ~/.cache/wal/mako-config ~/.config/mako/config
$ ln -sf ~/.cache/wal/alacritty.toml ~/.config/alacritty/alacritty.toml
```
Удалите репозиторий для освобождения места:
```sh
$ cd .. && rm -rf dotfiles/
```
## После установки
### Pywalfox
Плагин, который сделает цвета вашего браузера Firefox под цвет тех, что подобрала утилита wal

[Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/pywalfox/)  [GitHub](https://github.com/Frewacom/pywalfox)

### Walogram
По пути `~/.cache/walogram` лежит динамическая тема для TGD. Импортируйте ее в тг.

## Хоткеи
| Хоткей                        | Что делает  |
| ----------------------------- | ----------- | 
| <kbd>Win</kbd> + <kbd>W</kbd> | Выбор обоев |
| <kbd>Win</kbd> + <kbd>D</kbd> | Rofi        |
| <kbd>Win</kbd> + <kbd>X</kbd> | Kill        |
| <kbd>Win</kbd> + <kbd>R</kbd> | Emacs       |
| <kbd>Win</kbd> + <kbd>E</kbd> | Nautilus    |
| <kbd>Win</kbd> + <kbd>Q</kbd> | Alacritty   |
| <kbd>Win</kbd> + <kbd>P</kbd> | Power Menu  |
| <kbd>Win</kbd> + <kbd>L</kbd> | Hyprlock    |
| <kbd>Win</kbd> + <kbd>Z</kbd> | Magic       |
| <kbd>Win/Alt</kbd> + <kbd>S</kbd> | Grim    |

