FROM ubuntu:16.04

RUN apt-get update

RUN apt-get install -y wget

RUN apt-get install -y xz.utils #To untar files with xz extension

RUN apt-get install -y gcc

RUN apt-get install -y make

RUN apt-get install -y g++ #to install swig from sources. Not necessary for ubuntu>=18

RUN apt-get install -y zlib1g-dev #for python installation

RUN apt-get install -y libffi-dev #for ctype in python installation

RUN apt-get install -y libssl-dev #vérifier si nécessaire


RUN apt-get install -y perl 

RUN cd \
    wget https://www.openssl.org/source/openssl-1.1.1g.tar.gz \
    tar xvf openssl-1.1.1g.tar.gz \
    cd openssl-1.1.1g \
    ./config --prefix=/usr/openssl --openssldir=/usr/openssl no-ssl2 \
    make -j 8\
    make install\
    rm openssl-1.1.1g.tar.gz

