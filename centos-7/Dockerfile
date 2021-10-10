FROM centos:7 as base
MAINTAINER darkwizard242 <am900820@gmail.com>

## Due to error: (UnicodeEncodeError: 'ascii' codec can't encode character '\xe9' in position 117: ordinal not in range(128))
ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8

ENV DEPENDENCIES "which software-properties-common python3 python3-pip python3-setuptools sudo wget curl"

ENV PIP_PKGS "ansible"

RUN yum -y check-update || true \
    && yum -y update-minimal \
    && yum makecache fast \
    && yum install --setopt=install_weak_deps=False deltarpm epel-release initscripts -y \
    && yum -y check-update || true \
    && yum install --setopt=install_weak_deps=False ${DEPENDENCIES} @development -y \
    && python3 -m pip install --no-cache-dir -U pip wheel \
    && python3 -m pip install --no-cache-dir -U $PIP_PKGS \
    && for FILE in $(find /var/log -maxdepth 2 -type f); do echo "" > ${FILE}; done \
    && yum clean all

FROM base

# Initialize
CMD ["/bin/bash"]
