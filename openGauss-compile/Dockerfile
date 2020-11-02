FROM centos:7.6.1810
# Install necessary tools
RUN yum clean all \
    && yum makecache \
    && yum install -y wget vim git \
# Software dependency required in https://gitee.com/opengauss/openGauss-server
    && yum install -y libaio-devel flex bison ncureses-devel glibc-devel patch redhat-lsb-core readline-devel \
# Install Python3.6 and change the default python version
    && yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm \
    && yum install -y python36 \
    && mv /usr/bin/python /usr/bin/python.bak \
    && ln -s /usr/bin/python3 /usr/bin/python \
    && ln -s /usr/bin/pip3 /usr/bin/pip \
    && sed -i '1c #!/usr/bin/python2' /usr/bin/yum \
    && sed -i '1c #!/usr/bin/python2' /usr/libexec/urlgrabber-ext-down \
# Download files
    && mkdir /openGauss \
    && cd /openGauss \
    && wget -c https://opengauss.obs.cn-south-1.myhuaweicloud.com/1.0.1/openGauss-third_party_binarylibs.tar.gz \
    && tar -xzf openGauss-third_party_binarylibs.tar.gz \
    && mv openGauss-third_party_binarylibs /openGauss/binarylibs/ \
    && rm -f openGauss-third_party_binarylibs.tar.gz \
    && git clone https://gitee.com/opengauss/openGauss-server.git
