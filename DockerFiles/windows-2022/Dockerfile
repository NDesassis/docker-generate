FROM     mcr.microsoft.com/windows/nanoserver:ltsc2022

USER ContainerAdministrator

#ENV chocolateyUseWindowsCompression false

#RUN powershell -Command \
#    iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1')); \
#    choco feature disable --name showDownloadProgress

#RUN mkdir hdf5
RUN curl --progress-bar --location --output download.zip "https://www.hdfgroup.org/#package/cmake-hdf5-1-12-1-zip/?wpdmdl=15723"
#RUN powershell -Command choco install -y 7zip.install
#RUN powershell -Command dir
#RUN powershell -Command Expand-Archive -Path download.zip -DestinationPath hdf5



#RUN powershell -Command choco install python3 --version=3.7.3
#RUN cd CMake-hdf5-1-12-1
#RUN mkdir build
#RUN cd build
#RUN cmake -G "Visual Studio 17 2022" -DHDF5_GENERATE_HEADERS:BOOL=OFF -DBUILD_SHARED_LIBS:BOOL=OFF -#DDEFAULT_API_VERSION:STRING=v110 -DCMAKE_BUILD_TYPE:STRING=Release -DHDF5_BUILD_FORTRAN:BOOL=OFF -#DHDF5_BUILD_CPP_LIB:BOOL=ON -DHDF5_BUILD_JAVA:BOOL=OFF -#DCMAKE_INSTALL_PREFIX:PATH=C:#\hostedtoolcache\windows/hdf5 -DHDF5_ENABLE_SZIP_SUPPORT:BOOL=OFF -#DHDF5_ENABLE_Z_LIB_SUPPORT:BOOL=OFF -DBUILD_TESTING:BOOL=OFF -DHDF5_BUILD_TOOLS:BOOL=OFF ../hdf5-1-12-1
#RUN cmake --build . --target all --config Release
#RUN cmake --build . --target install --config Release
