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

RUN apt-get install -y git

RUN wget https://sourceforge.net/projects/swig/files/swig/swig-4.0.2/swig-4.0.2.tar.gz &&\
    tar -xvf swig-4.0.2.tar.gz &&\
    cd swig-4.0.2 &&\
    ./configure --without-pcre &&\
    make -j 8 &&\
    make install &&\
    cd .. &&\
    rm -rf swig-4.0.2*

RUN apt-get install -y libboost-dev

RUN apt-get install -y doxygen


RUN apt-get install -y perl &&\
    wget https://www.openssl.org/source/openssl-1.1.1g.tar.gz &&\
    tar xvf openssl-1.1.1g.tar.gz &&\
    cd openssl-1.1.1g &&\
    ./config --prefix=/usr/openssl --openssldir=/usr/openssl no-ssl2 &&\
    make -j 8 &&\
    make install &&\
    cd .. &&\
    rm -rf openssl-1.1.1g*

RUN apt-get install -y gfortran &&\
    apt-get install -y libbz2-dev &&\
    apt-get install -y liblzma-dev &&\
    apt-get install -y libpcre++-dev &&\
    apt-get install -y texlive-latex-extra &&\
    apt-get install -y libcurl4-openssl-dev &&\
    export JAVA_HOME="/opt/java/jre/" &&\
    export PATH=$PATH:$JAVA_HOME/bin

RUN wget https://cran.r-project.org/src/base/R-4/R-4.2.0.tar.gz &&\
    tar -xvf R-4.2.0.tar.gz &&\
    cd R-4.2.0 &&\
    ./configure --with-readline=no -with-x=no --with-pcre1 --enable-R-shlib &&\
    make &&\
    make install &&\
    cd .. &&\
    rm -rf R-4.2.0*


RUN wget https://www.python.org/ftp/python/3.5.10/Python-3.5.10.tgz &&\
    tar xvf Python-3.5.10.tgz &&\
    cd Python-3.5.10 &&\
    ./configure --prefix=/opt/python/py35/ &&\
    make -j 8 &&\
    make install &&\
    export PATH=/opt/python/py35/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin &&\
    python3 -m pip install twine &&\
    python3 -m pip install wheel &&\
    python3 -m pip install numpy &&\
    cd .. &&\
    rm -rf Python-3.5.10*

RUN wget https://www.python.org/ftp/python/3.6.15/Python-3.6.15.tgz &&\
    tar xvf Python-3.6.15.tgz &&\
    cd Python-3.6.15 &&\
    ./configure --prefix=/opt/python/py36/ &&\
    make -j 8 &&\
    make install &&\
    export PATH=/opt/python/py36/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin &&\
    python3 -m pip install --upgrade pip &&\
    python3 -m pip install twine &&\
    python3 -m pip install wheel &&\
    python3 -m pip install numpy &&\
    cd .. &&\
    rm -rf Python-3.6.15*

RUN wget https://www.python.org/ftp/python/3.7.12/Python-3.7.12.tgz &&\
    tar xvf Python-3.7.12.tgz &&\
    cd Python-3.7.12  &&\
    ./configure --prefix=/opt/python/py37/ &&\
    make -j 8 &&\
    make install &&\
    export PATH=/opt/python/py37/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin &&\
    python3 -m pip install twine &&\
    python3 -m pip install wheel &&\
    python3 -m pip install numpy &&\
    cd .. &&\
    rm -rf Python-3.7.12*

RUN wget https://www.python.org/ftp/python/3.8.12/Python-3.8.12.tgz &&\
    tar xvf Python-3.8.12.tgz &&\
    cd Python-3.8.12 &&\
    ./configure --prefix=/opt/python/py38/ &&\
    make -j 8 &&\
    make install &&\
    export PATH=/opt/python/py38/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin &&\
    python3 -m pip install twine &&\
    python3 -m pip install wheel &&\
    python3 -m pip install numpy &&\
    cd .. &&\
    rm -rf Python-3.8.12*

RUN wget https://www.python.org/ftp/python/3.9.10/Python-3.9.10.tgz &&\
    tar xvf Python-3.9.10.tgz &&\
    cd Python-3.9.10 &&\
    ./configure --prefix=/opt/python/py39/ &&\
    make -j 8 &&\
    make install &&\
    export PATH=/opt/python/py39/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin &&\
    python3 -m pip install twine &&\
    python3 -m pip install wheel &&\
    python3 -m pip install numpy &&\
    cd .. &&\
    rm -rf Python-3.9.10*


RUN wget https://www.python.org/ftp/python/3.10.2/Python-3.10.2.tgz &&\
    tar xvf Python-3.10.2.tgz &&\
    cd Python-3.10.2 &&\
    ./configure --prefix=/opt/python/py310/ --with-openssl=/usr/openssl --with-openssl-rpath=/usr/openssl/lib&&\
    make -j 8 &&\
    make install &&\
    export PATH=/opt/python/py310/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin &&\
    python3 -m pip install twine &&\
    python3 -m pip install wheel &&\
    python3 -m pip install numpy &&\
    cd .. &&\
    rm -rf Python-3.10.2*
    

RUN wget https://www.python.org/ftp/python/3.11.1/Python-3.11.1.tgz &&\
    tar xvf Python-3.11.1.tgz &&\
    cd Python-3.11.1 &&\
    ./configure --prefix=/opt/python/py311/ --with-openssl=/usr/openssl --with-openssl-rpath=/usr/openssl/lib&&\
    make -j 8 &&\
    make install &&\
    export PATH=/opt/python/py311/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin &&\
    python3 -m pip install twine &&\
    python3 -m pip install wheel &&\
    python3 -m pip install numpy &&\
    cd .. &&\
    rm -rf Python-3.11.1*
    

RUN git clone https://github.com/Kitware/CMake/ &&\
    cd CMake &&\
    ./bootstrap &&\
    make &&\ 
    make install &&\
    cd .. &&\
    rm -rf CMake


RUN wget https://support.hdfgroup.org/ftp/HDF5/releases/hdf5-1.12/hdf5-1.12.1/src/CMake-hdf5-1.12.1.tar.gz &&\
    tar -xvf CMake-hdf5-1.12.1.tar.gz &&\
    cd CMake-hdf5-1.12.1 &&\
    mkdir build &&\
    cd build &&\
    cmake -DHDF5_GENERATE_HEADERS:BOOL=OFF -DBUILD_SHARED_LIBS:BOOL=OFF -DDEFAULT_API_VERSION:STRING=v110 -DCMAKE_BUILD_TYPE:STRING=Release -DHDF5_BUILD_FORTRAN:BOOL=OFF -DHDF5_BUILD_CPP_LIB:BOOL=ON -DHDF5_BUILD_JAVA:BOOL=OFF -DCMAKE_INSTALL_PREFIX:PATH=/opt/hdf5-1.12.1 -DHDF5_ENABLE_SZIP_SUPPORT:BOOL=OFF -DHDF5_ENABLE_Z_LIB_SUPPORT:BOOL=OFF -DBUILD_TESTING:BOOL=OFF -DHDF5_BUILD_TOOLS:BOOL=OFF ../hdf5-1.12.1 &&\
    make -j 8 &&\
    make install &&\
    cd ../.. &&\
    rm -rf CMake-hdf5-1.12.1*





