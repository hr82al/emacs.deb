# emacs.deb
Repository with emacs.deb for ubuntu 29.4.50

## Emacs url link
https://www.gnu.org/software/emacs/

## Build emacs deb
### dev dependencies
```
apt-get update && apt-get install -y \
    build-essential \
    devscripts \
    dpkg-dev \
    fakeroot \
    lintian \
  	libtree-sitter-dev \
  	libmagickcore-dev \
  	libmagick++-dev \
  	libwebkit2gtk-4.1-dev \
  	dialog \
  	libgccjit-13-dev \
  	libgccjit0 \
  	libxpm-dev \
  	libgif-dev \
  	libjansson-dev \
  	libgnutls28-dev \gi
  	libncurses-dev \
  	mailutils \
  	texinfo \ 
```


```
./configure --with-x-toolkit=gtk3 --with-tree-sitter --with-native-compilation --with-json --with-mailutils --with-xwidgets --with-wide-int --with-imagemagick --prefix=/usr
make -j9
make install DESTDIR=/src/app
```

## control
```
Package: emacs-native
Version: 29.4
Section: editors
Priority: optional
Architecture: amd64
Depends: libwebpdecoder3 (>= 1.3.2), libmagickwand-6.q16-7t64 (>= 8:6.9.12), libgccjit0(>= 14.2.0), libtree-sitter0 (>= 0.20.8), install-info, dconf-gsettings-backend | gsettings-backend, init-system-helpers (>= 1.52), libacl1 (>= 2.2.23), libasound2t64 (>= 1.0.16), libc6 (>= 2.38), libcairo2 (>= 1.7.2), libdbus-1-3 (>= 1.9.14), libfontconfig1 (>= 2.12.6), libfreetype6 (>= 2.2.1), libgdk-pixbuf-2.0-0 (>= 2.22.0), libgif7 (>= 5.1), libglib2.0-0t64 (>= 2.79.0), libgmp10 (>= 2:6.3.0+dfsg), libgnutls30t64 (>= 3.8.2), libgpm2 (>= 1.20.7), libgtk-3-0t64 (>= 3.21.4), libharfbuzz0b (>= 0.9.42), libice6 (>= 1:1.0.0), libjansson4 (>= 2.14), libjpeg8 (>= 8c), liblcms2-2 (>= 2.2+git20110628), libm17n-0 (>= 1.6.1), libotf1 (>= 0.9.16), libpango-1.0-0 (>= 1.18.0), libpng16-16t64 (>= 1.6.2), librsvg2-2 (>= 2.52.5), libselinux1 (>= 3.1~), libsm6, libsqlite3-0 (>= 3.7.15), libsystemd0, libtiff6 (>= 4.0.3), libtinfo6 (>= 6), libwebpdemux2 (>= 1.3.2), libx11-6 (>= 2:1.2.99.901), libxcomposite1 (>= 1:0.4.5), libxext6, libxfixes3 (>= 1:4.0.1), libxi6 (>= 2:1.5.99.2), libxinerama1 (>= 2:1.1.4), libxml2 (>= 2.7.4), libxrandr2, libxrender1, zlib1g (>= 1:1.1.4)
Maintainer: hr82al <hr82al@gmail.com>
Description: The GNU Emacs editor (metapackage)
 GNU Emacs is the extensible, customizable, self-documenting real-time
 display editor. Compiled with native compile support.
 ```

## Make deb package
dpkg-deb --build emacs-native-29.4
