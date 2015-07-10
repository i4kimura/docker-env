FROM ubuntu:latest
MAINTAINER masayuki<masayuki.kimura.1986@gmail.com>

# install required package
RUN sed -i -e 's%http://archive.ubuntu.com/ubuntu%http://ftp.iij.ad.jp/pub/linux/ubuntu/archive%g' /etc/apt/sources.list

RUN apt-get update

RUN apt-get install -y \
    git \
    autoconf \
    automake \
    autotools-dev \
    curl \
    libmpc-dev \
    libmpfr-dev \
    libgmp-dev \
    gawk \
    build-essential \
    bison \
    flex \
    texinfo \
    gperf \
    gcc \
    libc6-dev \
    pkg-config \
    bridge-utils \
    uml-utilities \
    zlib1g-dev \
    libglib2.0-dev \
    autoconf \
    automake \
    libtool \
    libsdl1.2-dev \
    emacs

RUN git clone https://github.com/riscv/riscv-tools.git --recursive /riscv/
RUN sed -i 's/JOBS=16/JOBS=1/' /riscv/build.common
ENV TOP /riscv/
ENV RISCV /riscv/build/
ENV PATH /riscv/build/bin:${PATH}

RUN cd /riscv/ && ./build.sh
