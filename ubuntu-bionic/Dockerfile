FROM ubuntu:bionic
MAINTAINER darkwizard242 <am900820@gmail.com>

ENV dependencies "software-properties-common python3 python3-pip python3-setuptools python3-software-properties sudo systemd apt-transport-https  iputils-ping"

# Install required dependencies
RUN  DEBIAN_FRONTEND=non-interactive apt-get update -y \
     && DEBIAN_FRONTEND=non-interactive apt-get install $dependencies -y \
     && rm -rf /var/lib/apt/lists/* \
     && apt-get clean

ENV pip_pkgs "ansible"
#molecule flake8 ansible-lint molecule testinfra

# Install required packages
RUN python3 -m pip install -U pip wheel

RUN python3 -m pip install -U $pip_pkgs

COPY initctl_faker .
RUN chmod +x initctl_faker && rm -fr /sbin/initctl && ln -s /initctl_faker /sbin/initctl

# Volume mount requirement for systemd
VOLUME ["/sys/fs/cgroup", "/tmp", "/run"]

# Initialize
CMD ["/lib/systemd/systemd"]
