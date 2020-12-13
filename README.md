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
Replace the version number in the tags below with the version shown when running
`docker run --rm -it buildtools2019:latest` after creating the container.
```
cd buildtools
docker build -t buildtools2019:latest -m 2GB .
docker build -t buildtools2019-vctools:latest -m 2GB -f .\Dockerfile-vctools .
docker tag buildtools2019:ltsc2019-v16.8.3 buildtools2019:latest
docker tag buildtools2019-vctools:ltsc2019-v16.8.3 buildtools2019-vctools:latest
cd ..\addons
docker build -t dev:latest -m 2GB .
docker build -t dev-vctools:latest -m 2GB -f .\Dockerfile-vctools .
```

## Running
```
docker run --rm -it -v C:\Users\arneso\git\cppexample:C:\source -v C:\Users\arneso\git\build:C:\build dev-vctools:latest
```

## Export containers
```
docker save -o dev.tar dev:latest
docker save -o dev-vctools.tar dev-vctools:latest
```

## Import containers
```
docker load < dev.tar
docker load < dev-vctools.tar
```
