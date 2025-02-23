FROM ubuntu:24.04

# Set environment variables to avoid interactive prompts
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Etc/UTC

RUN apt update && \
    apt install --no-install-recommends -y \
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
      libgnutls28-dev \
      libncurses-dev \
      mailutils \
      texinfo \
      neovim \
      apt-file && \
      apt-file update && \
      rm -rf /var/lib/apt/lists/*
WORKDIR /app