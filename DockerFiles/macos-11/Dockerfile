FROM     sickcodes/docker-osx

RUN mkdir hdf5
RUN curl --progress-bar --location --output hdf5/download.tar.gz "https://www.hdfgroup.org/package/cmake-hdf5-1-12-1-tar-gz/?wpdmdl=15722" 
RUN /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
RUN brew install p7zip
RUN 7z -o=hdf5 x hdf5/download.tar.gz
RUN cd hdf5 &&\
    cd CMake-hdf5-1-12-1 &&\
    cmake -G -DHDF5_GENERATE_HEADERS:BOOL=OFF -DBUILD_SHARED_LIBS:BOOL=OFF -DDEFAULT_API_VERSION:STRING=v110 -DCMAKE_BUILD_TYPE:STRING=Release -DHDF5_BUILD_FORTRAN:BOOL=OFF -DHDF5_BUILD_CPP_LIB:BOOL=ON -DHDF5_BUILD_JAVA:BOOL=OFF -DCMAKE_INSTALL_PREFIX:PATH=C:C:\\Temp\\hdf5 -DHDF5_ENABLE_SZIP_SUPPORT:BOOL=OFF -DHDF5_ENABLE_Z_LIB_SUPPORT:BOOL=OFF -DBUILD_TESTING:BOOL=OFF -DHDF5_BUILD_TOOLS:BOOL=OFF ..\\hdf5-1-12-1 &&\
    cmake --build . --target all --config Release &&\
    cmake --build . --target install --config Release 
