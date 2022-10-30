# Terminal

## Showing picture to terminal

### Dependencies

#### catimg

Renders images in the terminal.

```sh
git clone https://github.com/posva/catimg
cd catimg
cmake .
make install
cd -
```

#### chafa

Image to text.

```sh
emerge -av 
```

#### Other dependencies from official packages

Must enable imlib on w3m

```sh
emerge -av \
media-gfx/w3mimgfb \
media-gfx/imagemagick \
media-gfx/chafa \
media-gfx/feh \
media-gfx/jp2a \
media-libs/libcaca \
x11-misc/nitrogen \
x11-misc/xdotool \
x11-apps/xdpyinfo \
x11-apps/xprop \
x11-apps/xrandr \
x11-apps/xwininfo
```

## Terminal(kitty)

```sh
emerge -av x11-terms/kitty
```

### Add Blur

Add the script to `~/.bashrc`.  
**Note: It only works with KDE.**

```sh
if [[ $(ps --no-header -p $PPID -o comm | grep -Ev '^(yakuake|konsole)$' ) ]]; then
        for wid in $(xdotool search --pid $PPID); do
            xprop -f _KDE_NET_WM_BLUR_BEHIND_REGION 32c -set _KDE_NET_WM_BLUR_BEHIND_REGION 0 -id $wid; done
fi
```

### kitty themes

```sh
git clone https://github.com/dexpota/kitty-themes ~/.config/kitty/themes
```

You can change theme, with adding the below line to `~/.config/kitty.conf`.  
**Note: You have to write in the end, when color customization is written in the config.**

```conf
include themes/themes/Monokai_Pro_(Filter_Machine).conf
```
