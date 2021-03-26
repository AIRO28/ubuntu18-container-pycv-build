# '''Dockerfile for Ubuntu18.04 + python3.6.x'''

# Set Ubuntu 18.04 as the base image.
FROM ubuntu:18.04

# Disable interactive installation.
ENV DEBIAN_FRONTEND=noninteractive

# Describe the packages to be installed at build time.
RUN apt update && apt upgrade -y && \
    apt install -y cmake \
    gcc \
    g++ \
    git \
    tzdata \
    xterm

# Set time zone to Asia/Tokyo
ENV TZ=Asia/Tokyo

# Install the python3.6.x package.
RUN apt install -y python3.6 \
    python3-pip \
    python3-dev \
    python3-setuptools \
    python3-numpy \
    python3-tk

# Install the packages required to build Opencv.
RUN apt install -y libavcodec-dev \
    libavformat-dev \
    libswscale-dev \
    libgstreamer-plugins-base1.0-dev \
    libgstreamer1.0-dev \
    libgtk-3-dev \
    libpng-dev \
    libjpeg-dev \
    libopenexr-dev \
    libtiff-dev \
    libwebp-dev

# Clone the Opencv repository.
RUN git clone https://github.com/opencv/opencv.git

# Run the Opencv build.
RUN cd opencv && \
    mkdir builds && \
    cd builds && \
    cmake .. && \
    make && \
    make install

# Setting the Japanese Locale
RUN apt install -y locales && \
    locale-gen ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL=ja_JP.UTF-8
RUN localedef -f UTF-8 -i ja_JP ja_JP.utf8

# Metadata description.
LABEL maintainer="https://twitter.com/AIRO28_" \
    version="1.0" \
    description="Ubuntu18.04 container with opencv-python"

# Instructions to be executed at container startups.
CMD ["/bin/bash"]
