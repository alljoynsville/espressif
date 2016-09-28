FROM ubuntu:trusty

RUN export DEBIAN_FRONTEND=noninteractive && \
    apt-get -yqq update && \
    apt-get -yqq install make unrar-free autoconf automake libtool gcc g++ gperf \
                         flex bison texinfo gawk ncurses-dev libexpat-dev python-dev python python-pip python-serial \
                         sed git-core subversion unzip help2man wget bzip2 gawk vim less && \
    apt-get clean && \
    useradd  --create-home --home-dir /builder --shell /bin/bash builder && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

WORKDIR  /builder
USER builder
RUN  git clone --recursive https://github.com/pfalcon/esp-open-sdk.git && \
     cd esp-open-sdk/ && \
     make STANDALONE=y

CMD ["/bin/bash"]

