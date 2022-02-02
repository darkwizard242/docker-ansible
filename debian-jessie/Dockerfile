FROM debian:jessie
LABEL maintainer="Ali Muhammad"

ENV dependencies "software-properties-common python3 python3-pip python3-setuptools python3-software-properties sudo apt-transport-https iputils-ping wget curl"

# Install required dependencies
RUN  DEBIAN_FRONTEND=non-interactive apt-get update -y \
     && DEBIAN_FRONTEND=non-interactive apt-get upgrade -y \
     && DEBIAN_FRONTEND=non-interactive apt-get install $dependencies -y \
     && rm -rf /var/lib/apt/lists/* /var/cache/apt/archives/*.deb \
     && apt-get autoremove \
     && apt-get clean

ENV pip_pkgs "ansible"
#molecule flake8 ansible-lint molecule testinfra

# Install required packages
RUN python3 -m pip install -U pip wheel \
    && python3 -m pip install -U $pip_pkgs

# Initialize
CMD ["/bin/bash"]
