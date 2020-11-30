FROM centos:8 as base
MAINTAINER darkwizard242 <am900820@gmail.com>

ENV DEPENDENCIES "which python3 python3-pip python3-setuptools sudo wget curl"

ENV PIP_PKGS "ansible"

# Install required dependencies
RUN dnf check-update -y  || true \
    && dnf upgrade-minimal -y \
    && dnf install --setopt=install_weak_deps=False epel-release initscripts -y \
    && dnf check-update -y  || true \
    && dnf install --setopt=install_weak_deps=False ${DEPENDENCIES} -y \
    && python3 -m pip install --no-cache-dir -U pip wheel \
    && python3 -m pip install --no-cache-dir -U $PIP_PKGS \
    && for FILE in $(find /var/log -maxdepth 2 -type f); do echo "" > ${FILE}; done \
    && dnf autoremove -y \
    && dnf clean all \
    && rm -rf /tmp/

FROM base

# Initialize
CMD ["/bin/bash"]
