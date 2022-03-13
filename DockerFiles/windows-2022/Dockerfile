#FROM mcr.microsoft.com/powershell
FROM ndesassis/test_windows-2022
#USER ContainerAdministrator

SHELL ["cmd", "/S", "/C"]

###################################################################################################
# Installation of VS components
#https://jfreeman.dev/blog/2019/07/09/what-i-learned-making-a-docker-container-for-building-c++-on-windows/
#ADD https://aka.ms/vs/16/release/vs_buildtools.exe C:\\Temp\\vs_buildtools.exe
#ADD https://aka.ms/vs/16/release/channel C:\\Temp\\VisualStudio.chman

#RUN C:\\Temp\\vs_buildtools.exe \
#    --quiet --wait --norestart --nocache \
#    --installPath C:\\BuildTools \
#    --channelUri C:\\Temp\\VisualStudio.chman \
#    --installChannelUri C:\\Temp\\VisualStudio.chman \
#    --add Microsoft.VisualStudio.Workload.VCTools;includeRecommended \
#    --add Microsoft.Component.MSBuild || IF "%ERRORLEVEL%"=="3010" EXIT 0

####################################################################################

#RUN powershell.exe -ExecutionPolicy RemoteSigned \
#  iex (new-object net.webclient).downloadstring('https://get.scoop.sh'); \
#  scoop install python git


#RUN mkdir hdf5
#RUN curl --progress-bar -o .\\hdf5\\download.tar.gz "https://www.hdfgroup.org/package/cmake-hdf5-1-12-1-tar-gz/?wpdmdl=15722" 
RUN dir
RUN cd hdf5 &&\
    tar -xf hdf5\\download.tar.gz
RUN cd hdf5\\CMake-hdf5-1-12-1 &&\cmake -G "Visual Studio 17 2022" -DHDF5_GENERATE_HEADERS:BOOL=OFF -DBUILD_SHARED_LIBS:BOOL=OFF -DDEFAULT_API_VERSION:STRING=v110 -DCMAKE_BUILD_TYPE:STRING=Release -DHDF5_BUILD_FORTRAN:BOOL=OFF -DHDF5_BUILD_CPP_LIB:BOOL=ON -DHDF5_BUILD_JAVA:BOOL=OFF -DCMAKE_INSTALL_PREFIX:PATH=C:C:\\Temp\\hdf5 -DHDF5_ENABLE_SZIP_SUPPORT:BOOL=OFF -DHDF5_ENABLE_Z_LIB_SUPPORT:BOOL=OFF -DBUILD_TESTING:BOOL=OFF -DHDF5_BUILD_TOOLS:BOOL=OFF ..\\hdf5-1-12-1 &&\
    cmake --build . --target all --config Release &&\
    cmake --build . --target install --config Release 




#ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&
#CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]







#ENV chocolateyUseWindowsCompression false

#RUN powershell -Command \
#    iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1')); \
#    choco feature disable --name showDownloadProgress



#RUN powershell -Command choco install -y 7zip.install


#RUN curl --progress-bar -o download.tar.bz2 https://sourceforge.net/projects/boost/files/boost/1.72.0/boost_1_72_0.tar.bz2/download &&\
    





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
