FROM ubuntu:trusty

RUN apt-get -yqq update && \
    apt-get -yqq install make unrar-free autoconf automake libtool gcc g++ gperf \
    flex bison texinfo gawk ncurses-dev libexpat-dev python-dev python python-serial \
    sed git-core subversion unzip help2man wget bzip2 gawk vim less && \
	  apt-get clean && \
	useradd  --create-home --home-dir /builder --shell /bin/bash builder && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

WORKDIR  /builder
USER builder
CMD ["/bin/bash"]
