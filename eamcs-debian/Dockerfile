FROM debian:bookworm-20250203

RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y \
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
    libgccjit-12-dev \
    libgccjit0 \
    libxpm-dev \
    libgif-dev \
    libjansson-dev \
    libgnutls28-dev \
    libncurses-dev \
    mailutils \
    texinfo \
    libxaw7-dev

WORKDIR /app
VOLUME /app

CMD ["bash"]
