# docker-ansible

[![](https://github.com/darkwizard242/docker-ansible/workflows/docker-automated-build/badge.svg)](https://github.com/darkwizard242/docker-ansible/actions) ![Docker Pulls](https://img.shields.io/docker/pulls/darkwizard242/ansible?color=yellow) ![GitHub](https://img.shields.io/github/license/darkwizard242/docker-ansible)

Docker images that contains ansible and/or any pre-requistes installed within the images. Purpose of these container images is to provide users with easy to use ansible docker containers as well as for easily ready images for facilitating molecule testing of ansible roles during development.

## Supported tags and Dockerfile:

For Ubuntu 18.04 (bionic), docker tag and Dockerfile:

- [ubuntu-18.04](https://github.com/darkwizard242/docker-ansible/blob/master/ubuntu-bionic/Dockerfile)

For Ubuntu 16.04 (xenial), docker tag and Dockerfile:

- [ubuntu-16.04](https://github.com/darkwizard242/docker-ansible/blob/master/ubuntu-xenial/Dockerfile)

For CentOS 7, docker tag and Dockerfile:

- [centos-7](https://github.com/darkwizard242/docker-ansible/blob/master/centos-7/Dockerfile)

For Debian 10 (buster), docker tag and Dockerfile:

- [debian-buster](https://github.com/darkwizard242/docker-ansible/blob/master/debian-buster/Dockerfile)

For Debian 9 (stretch), docker tag and Dockerfile:

- [debian-stretch](https://github.com/darkwizard242/docker-ansible/blob/master/debian-stretch/Dockerfile)

For Debian 8 (jessie), docker tag and Dockerfile:

- [debian-jessie](https://github.com/darkwizard242/docker-ansible/blob/master/debian-jessie/Dockerfile)

## How to use:

Simply, pull the docker image using whichever tag you prefer or run it directly.

### 1\. Ubuntu 18.04:

```shell
docker run -it darkwizard242/ansible:ubuntu-18.04 /bin/bash
```

### 2\. Ubuntu 16.04:

```shell
docker run -it darkwizard242/ansible:ubuntu-16.04 /bin/bash
```

### 3\. CentOS 7:

```shell
docker run -it darkwizard242/ansible:centos-7 /bin/bash
```

### 4\. Debain 10 (Buster):

```shell
docker run -it darkwizard242/ansible:debian-buster /bin/bash
```

### 5\. Debain 9 (Stretch):

```shell
docker run -it darkwizard242/ansible:debian-stretch /bin/bash
```

### 6\. Debain 8 (Jessie):

```shell
docker run -it darkwizard242/ansible:debian-jessie /bin/bash
```

## Author:

Created by [Ali Muhammad](https://www.linkedin.com/in/ali-muhammad-759791130/), a DevOps/CloudOps Engineer who loves to learn and contribute to Open Source community.
