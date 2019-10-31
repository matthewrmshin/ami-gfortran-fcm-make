# ami-gfortran-fcm-make

Dockerfile based on [Amazon Linux 1](https://hub.docker.com/_/amazonlinux) with:
* [GFortran](https://gcc.gnu.org/wiki/GFortran)
* [FCM Make](https://github.com/metomi/fcm/) - the Fortran build system.

Build the image:

`docker build . --tag 'ami-gfortran-fcm-make'`

Use the image to run `fcm make` to build the Fortran source tree in the current
working directory:

`docker run --rm -t -i -u "$(id -u):$(id -g)" -v "$PWD:/opt/myapp" 'ami-gfortran-fcm-make' fcm make -C /opt/myapp`
