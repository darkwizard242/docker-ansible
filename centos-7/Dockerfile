FROM centos:7
MAINTAINER darkwizard242 <am900820@gmail.com>

ENV dependencies "which software-properties-common python36 python36-pip python36-setuptools sudo systemd"

# Install required dependencies
RUN  yum install epel-release -y \
     && yum update -y \
     && yum install $dependencies -y \
     && yum clean all

ENV pip_pkgs "ansible" 
#molecule flake8 ansible-lint molecule testinfra

# Install required packages
RUN python36 -m pip install -U pip wheel

RUN python36 -m pip install -U $pip_pkgs

# Initialize

CMD ["/bin/bash"]
