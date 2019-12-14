FROM centos:7
MAINTAINER darkwizard242 <am900820@gmail.com>

RUN yum -y update \
    && yum clean all

ENV dependencies "which software-properties-common python3 python3-pip python3-setuptools sudo wget curl"

# Install required dependencies
RUN yum makecache fast \
    && yum install deltarpm epel-release initscripts -y \
    && yum update -y \
    && yum install $dependencies @development -y \
    && yum clean all

ENV pip_pkgs "ansible"
#molecule flake8 ansible-lint molecule testinfra

# Install required packages
RUN python3 -m pip install -U pip wheel \
    && python3 -m pip install -U $pip_pkgs

# Initialize
CMD ["/bin/bash"]
