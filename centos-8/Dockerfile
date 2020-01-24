FROM centos:8
MAINTAINER darkwizard242 <am900820@gmail.com>

ENV dependencies "which python3 python3-pip python3-setuptools sudo wget curl"

# Install required dependencies
RUN dnf update -y \
    && dnf upgrade -y \
    && dnf install epel-release initscripts -y \
    && dnf update -y \
    && dnf install $dependencies -y \
    && dnf clean all

# Install required pip modules
RUN python3 -m pip install -U pip wheel \
    && python3 -m pip install -U ansible

# Initialize
CMD ["/bin/bash"]
