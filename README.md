# docker-windows
Dockerfiles for windows build containers, tested on Windows Server 2019.

## buildtools
The buildtools directory contains Dockerfiles for building base buildtools containers as
described on
https://docs.microsoft.com/en-us/visualstudio/install/build-tools-container?view=vs-2019

Naming convention for containers, example: `buildtools2019:ltsc2019-v16.5.4`

The `-vctools` files are for building visual c++ containers. The plain Dockerfile are for
building dotnet containers. 

## addons
The addons directory contains Dockerfiles adding tool likes Chocolatey, CMake, Python and Conan.
to the base containers.

## Build containers
```
docker build -t buildtools2019:ltsc2019-v16.5.4 -m 2GB .
docker build -t buildtools2019-vctools:ltsc2019-v16.5.4 -m 2GB -f .\Dockerfile-vctools .
docker build -t dev:latest -m 2GB .
docker build -t dev-vctools:latest -m 2GB -f .\Dockerfile-vctools .
```

## Running
```
docker run --rm -it -v C:\Users\arneso\git\cppexample:C:\source -v C:\Users\arneso\git\build:C:\build dev-vctools:latest
```
