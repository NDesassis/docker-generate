FROM     mcr.microsoft.com/windows/nanoserver:ltsc2022
RUN dir
RUN mkdir hdf5
RUN curl --progress-bar --location --output hdf5/download.zip "https://www.hdfgroup.org/#package/cmake-hdf5-1-12-1-zip/?wpdmdl=15723"
RUN 7z x hdf5/download.zip
RUN cd CMake-${{env.HDF5_VERSION}}
RUN mkdir build
RUN cd build
RUN cmake -G "Visual Studio 17 2022" -DHDF5_GENERATE_HEADERS:BOOL=OFF -DBUILD_SHARED_LIBS:BOOL=OFF -DDEFAULT_API_VERSION:STRING=v110 -DCMAKE_BUILD_TYPE:STRING=Release -DHDF5_BUILD_FORTRAN:BOOL=OFF -DHDF5_BUILD_CPP_LIB:BOOL=ON -DHDF5_BUILD_JAVA:BOOL=OFF -DCMAKE_INSTALL_PREFIX:PATH=C:\hostedtoolcache\windows/hdf5 -DHDF5_ENABLE_SZIP_SUPPORT:BOOL=OFF -DHDF5_ENABLE_Z_LIB_SUPPORT:BOOL=OFF -DBUILD_TESTING:BOOL=OFF -DHDF5_BUILD_TOOLS:BOOL=OFF ../hdf5-1-12-1
RUN cmake --build . --target all --config Release
RUN cmake --build . --target install --config Release
