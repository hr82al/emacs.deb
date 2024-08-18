# emacs.deb
Repository with emacs.deb for ubuntu 29.4.50

## Emacs url link
https://www.gnu.org/software/emacs/

## Build emacs deb
mkdir home
apt-get install -y \
	git \
	apt-transport-https \
        ca-certificates \
        curl \
        gnupg-agent \
        software-properties-common \
	build-essential \
	checkinstall \
	texinfo 
apt-get install -y gcc-12 \
	libgccjit0 \
	libgccjit-12-dev \
	libjansson4 \
	libjansson-dev \
	gnutls-bin \
	libtree-sitter-dev \
	imagemagick \
	libmagick++-dev \
	libwebp-dev \
	webp \
	libxft-dev \
	libxft2 \
	libxaw7-dev \
	libgif-dev \
	libgnutls28-dev \
	libncurses-dev \
	libharfbuzz-dev

cd /root
mkdir emacs
cd emacs
git clone https://git.savannah.gnu.org/git/emacs.git -b emacs-29
./autogen.sh
cd ..
mkdir build
cd build

./configure --without-compress-install --with-json --with-native-compilation --with-x-toolkit=lucid --with-tree-sitter --with-mailutils --prefix=/usr
make -j9


copy content to deb package


## Make deb package
dpkg-deb --build hemacs-29.4.50-amd64
