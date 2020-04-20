# escape=`

# Use the latest Windows Server Core image with .NET Framework 4.8.
FROM buildtools2019

# Install Chocolatey
RUN powershell [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

RUN powershell choco install cmake --installargs 'ADD_CMAKE_TO_PATH=System' -y; choco install ninja -y

