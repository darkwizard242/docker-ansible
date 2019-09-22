FROM centos:7
MAINTAINER darkwizard242 <am900820@gmail.com>

RUN yum -y update; yum clean all; \
(cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*;

ENV dependencies "which software-properties-common python3 python3-pip python3-setuptools sudo systemd"

# Install required dependencies
RUN  yum install epel-release -y \
     && yum update -y \
     && yum install $dependencies -y \
     && yum clean all

ENV pip_pkgs "ansible"
#molecule flake8 ansible-lint molecule testinfra

# Install required packages
RUN python3 -m pip install -U pip wheel

RUN python3 -m pip install -U $pip_pkgs

# Initialize

CMD ["/usr/lib/systemd/systemd"]
