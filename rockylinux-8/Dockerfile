FROM rockylinux:8 as base
LABEL maintainer="Ali Muhammad"

ENV DEPENDENCIES "which python3.12 python3.12-pip python3.12-setuptools sudo wget curl"

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
    && dnf clean all

FROM base

# Initialize
CMD ["/bin/bash"]
