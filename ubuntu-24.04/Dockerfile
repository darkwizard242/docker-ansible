FROM ubuntu:noble as base
LABEL maintainer="Ali Muhammad"

ENV DEPENDENCIES "software-properties-common python3 python3-pip python3-pip-whl python3-setuptools python3-software-properties sudo apt-transport-https iputils-ping wget curl gnupg gcc python3-dev xz-utils"

ENV PIP_PKGS "ansible"

# Install required dependencies
RUN  DEBIAN_FRONTEND=non-interactive apt-get update -y \
     && DEBIAN_FRONTEND=non-interactive apt-get --no-install-recommends -y upgrade \
     && DEBIAN_FRONTEND=non-interactive apt-get install --no-install-recommends -y ${DEPENDENCIES} \
     && find /usr/lib/python3* -type f -name EXTERNALLY-MANAGED -exec rm -v {} \; \
     && python3 -m pip install --no-cache-dir -U ${PIP_PKGS} \
     && rm -rf /var/lib/apt/lists/* /var/cache/apt/archives/*.deb \
     && for FILE in $(find /var/log -maxdepth 2 -type f); do echo "" > ${FILE}; done \
     && apt-get autoremove \
     && apt-get clean

FROM base

# Initialize
CMD ["/bin/bash"]
