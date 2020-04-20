# escape=`

# Use the latest Windows Server Core image with .NET Framework 4.8.
FROM buildtools2019

# Install Chocolatey
RUN powershell [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

RUN powershell choco install python -y --version=3.7.7;
RUN powershell choco install cmake --installargs 'ADD_CMAKE_TO_PATH=System' -y --version=3.17.1; `
    choco install ninja -y --version=1.10.0; `
    python -m pip install --upgrade pip; pip install conan==1.24.0; `
    choco install jfrog-cli -y --version=1.35.3

# Uncomment the lines below for latest versions
#RUN powershell choco install cmake --installargs 'ADD_CMAKE_TO_PATH=System' -y; `
#    choco install ninja -y; `
#    python -m pip install --upgrade pip; pip install conan; `
#    choco install jfrog-cli -y
