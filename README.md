# st - simple terminal
--------------------
st is a simple terminal emulator for X which sucks less.


Requirements
------------
In order to build st you need the Xlib header files.


Installation
------------
Edit config.mk to match your local setup (st is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install st (if
necessary as root):

    make clean install


Running st
----------
If you did not install st with make clean install, you must compile
the st terminfo entry with the following command:

    tic -sx st.info

See the man page for additional details.

Credits
-------
Based on Aurélien APTEL <aurelien dot aptel at gmail dot com> bt source code.

## Input Methods

[archlinux fcitx5-rime](https://wiki.archlinux.org/title/Fcitx5_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)#%E8%BE%93%E5%85%A5%E6%B3%95%E5%BC%95%E6%93%8E)

Install: `fcitx5` `fcitx5-im` `fcitx5-configtool` `fcitx5-gtk` `fcitx5-qt` `fcitx5-material-color` `fcitx5-rime`

fcitx5-im中包括fcitx5、fcitx5-configtool、fcitx5-gtk、fcitx5-qt

- fcitx5: 输入法基础框架主程序

- fcitx5-configtool：输入法配置程序

- fcitx5-qt: QT5程序的支持 

- fcitx5-gtk: GTK程序的支持 

- fcitx5-rime:中文输入法引擎，对经典的 Rime IME 输入法的包装，内置了繁体中文和简体中文的支持
[rime 四叶草拼音输入方案](https://github.com/fkxxyz/rime-cloverpinyin)

- fcitx5-material-color：一款使用 Material Design 配色的 fcitx5 皮肤，旨在模仿 Windows 10 自带输入法的 UI


And in `/etc/X11/xinit/xinitrc`:
```
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS="@im=fcitx"
```

#### Fcitx users need to set the first input method to be Keyboard - layout

## fonts
#### locale
In `locale.conf`:
```
LANG=en_US.UTF-8
LC_ADDRESS=en_US.UTF-8
LC_IDENTIFICATION=en_US.UTF-8
LC_MEASUREMENT=en_US.UTF-8
LC_MONETARY=en_US.UTF-8
LC_NAME=en_US.UTF-8
LC_NUMERIC=en_US.UTF-8
LC_PAPER=en_US.UTF-8
LC_TELEPHONE=en_US.UTF-8
LC_TIME=en_US.UTF-8
```

#### My Font
I use the `Source Code Pro` font and `nerd-fonts-source-code-pro`.

#### About Noto
Just install `noto-fonts` (not `-all`). It's already bloated. Check `/usr/share/fonts/noto`

#### Emoji
```
yay -S ttf-linux-libertine ttf-inconsolata ttf-joypixels ttf-twemoji-color noto-fonts-emoji ttf-liberation ttf-droid
```

#### Chinese
```
yay -S wqy-bitmapfont wqy-microhei wqy-microhei-lite wqy-zenhei adobe-source-han-mono-cn-fonts adobe-source-han-sans-cn-fonts adobe-source-han-serif-cn-fonts
```

# patch
#### anysize 
让st占满整个屏幕
#### alpha
设置透明度
#### dracula
st的一个颜色配置
#### scrollback
让终端翻页
#### fontfix
对于无法显示的字体，更好的显示
#### hidecursor
在终端打字时将光标隐藏
#### externalpipe
复制终端输出内容，复制url，打开url
