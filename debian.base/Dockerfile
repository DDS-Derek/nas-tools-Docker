FROM debian:11-slim

RUN set -xe && \
    export DEBIAN_FRONTEND="noninteractive" && \
    apt-get update -y && \
    # Python3.10
    apt-get install -y \
        build-essential \
        zlib1g-dev \
        libncurses5-dev \
        libgdbm-dev \
        libnss3-dev \
        libssl-dev \
        libreadline-dev \
        libffi-dev \
        libsqlite3-dev \
        wget \
        curl \
        libbz2-dev && \
    wget https://www.python.org/ftp/python/3.10.10/Python-3.10.10.tgz -O /tmp/python3.tgz && \
    mkdir -p /tmp/python3 && \
    tar -xf /tmp/python3.tgz -C /tmp/python3 --strip-components 1 && \
    cd /tmp/python3 && \
    ./configure && \
    make -j 4 && \
    make altinstall && \
    # Clear
    apt-get remove -y build-essential && \
    apt-get autoremove -y && \
    apt-get clean -y && \
    rm -rf \
        /tmp/* \
        /root/.cache \
        /var/lib/apt/lists/* \
        /var/tmp/*
