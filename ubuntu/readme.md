```
./configure --with-x-toolkit=gtk3 --with-tree-sitter --with-native-compilation --with-json --with-mailutils --with-xwidgets --with-wide-int --with-imagemagick --prefix=/usr
make -j9
make install DESTDIR=/app/emacs-nativ
```

```
./configure --with-x-toolkit=no --with-tree-sitter --with-native-compilation --with-json --with-mailutils --with-wide-int  --without-png --without-tiff  --without-jpeg --without-gif --without-xpm  --without-webp --without-rsvg --without-dbus --without-lcms2 --without-cairo --without-xft --without-harfbuzz --without-libotf --without-m17n-flt --without-xaw3d --without-xim  --without-xdbe --prefix=/usr

```



```
dpkg-deb --build emacs-native
```

```
for i in $(seq 1 10) ; do nala install  $(apt-file search $(emacs 2>&1 | cut -d ':' -f 3 | tee -a /app/p) | tee -a /app/p | sed -n '1 p' | cut -d ':' -f 1 | tee -a /app/l) -y ; done
```

```
while IFS= read -r line ; do echo "$line (>= $(apt show $line 2>/dev/null | grep Version | grep -oP '\d+\.\d+[0-9\.]+'))," >> /app/r ; done < /app/l
```

```
docker build --platform=linux/amd64 -t my-ubuntu .
```

```
docker build --platform=linux/arm64/v8 -t my-ubuntu-aarch64 .
```

```
 docker run --rm -it --name u1 -v ./app:/app my-ubuntu bash
```

```
docker run --rm -it -v ./app:/app my-ubuntu-aarch64 bash
```