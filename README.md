# OpenGaussDockerfile
openGauss dockerfile to build environment.


In directory openGauss-compile:


Dockerfile to build a compile environment for openGauss.

## How to use

```bash
cd openGauss-compile
docker build -t opengauss_compile:1.0.1 .
docker run -it opengauss_compile:1.0.1 /bin/bash
cd /openGauss/openGauss-server
./build -m debug -3rd /openGauss/binarylibs -pkg
# then you can find openGauss-1.0.1-CentOS-64bit.tar.gz in /openGauss/openGauss-server/package
```
