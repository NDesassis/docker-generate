#FROM     mcr.microsoft.com/windows/nanoserver:ltsc2022

FROM mcr.microsoft.com/powershell
#USER ContainerAdministrator

SHELL ["cmd", "/S", "/C"]

RUN `
    # Download the Build Tools bootstrapper.
    curl -SL --output vs_buildtools.exe https://aka.ms/vs/17/release/vs_buildtools.exe `
    `
    # Install Build Tools with the Microsoft.VisualStudio.Workload.AzureBuildTools workload, excluding workloads and components with known issues.
    && (start /w vs_buildtools.exe --quiet --wait --norestart --nocache `
        --installPath "%ProgramFiles(x86)%\Microsoft Visual Studio\2022\BuildTools" `
        --add Microsoft.VisualStudio.Workload.AzureBuildTools `
        --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
        --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
        --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
        --remove Microsoft.VisualStudio.Component.Windows81SDK `
        || IF "%ERRORLEVEL%"=="3010" EXIT 0) `
    `
    # Cleanup
    && del /q vs_buildtools.exe

# Define the entry point for the docker container.
# This entry point starts the developer command prompt and launches the PowerShell shell.
ENTRYPOINT ["C:\\Program Files (x86)\\Microsoft Visual Studio\\2022\\BuildTools\\Common7\\Tools\\VsDevCmd.bat", "&&", "powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]












#ENV chocolateyUseWindowsCompression false

#RUN powershell -Command \
    iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1')); \
    choco feature disable --name showDownloadProgress



#RUN powershell -Command choco install -y 7zip.install


#RUN curl --progress-bar -o download.tar.bz2 https://sourceforge.net/projects/boost/files/boost/1.72.0/boost_1_72_0.tar.bz2/download &&\
    

#RUN mkdir hdf5
#RUN curl --progress-bar -o download.tar.gz "https://www.hdfgroup.org/package/cmake-hdf5-1-12-1-tar-gz/?wpdmdl=15722" &&\
#    dir &&\
#    tar -xf download.tar.gz




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
