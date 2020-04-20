# docker-windows
Dockerfiles for windows build containers, tested on Windows Server 2019.

## buildtools
The buildtools directory contains Dockerfiles for building base buildtools containers as described on
https://docs.microsoft.com/en-us/visualstudio/install/build-tools-container?view=vs-2019

Naming convention for containers, example: `buildtools2019:ltsc2019-v16.5.4`

## addons
The addons directory contains Dockerfiles adding tool likes Chocolatey, CMake, Python and Conan.
to the base containers.
