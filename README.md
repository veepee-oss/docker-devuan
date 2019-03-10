# docker-devuan

[![License][license-img]][license-href]
[![docker][docker-img]][docker-href]

1. [Overview](#overview)
2. [Description](#description)
3. [Tags](#tags)
4. [Setup](#setup)
5. [Usage](#usage)
6. [Limitations](#limitations)
7. [Development](#development)
8. [Miscellaneous](#miscellaneous)

## Overview

Devuan is  a free software  operating system  for your computer.  Free software
means you are free to use, copy and distribute, study, change the software, and
share your modifications with the community.

[devuan.org][overview-href]

## Description

Use this script to build your own base system.

## Tags

Supported tags.

- 1, 1.0, jessie, oldstable
- 2, 2.0, ascii, stable, latest

## Setup

On Debian you need sudo permissions and the following packages:

```bash
# if you build on wheezy please use backports version of debootstrap
sudo apt-get -qq -y install debootstrap
```

On Devuan you need sudo permissions and the following packages:

```bash
sudo apt-get -qq -y install debootstrap
```

On Ubuntu you need sudo permissions and the following packages:

```bash
sudo apt-get -qq -y install debian-keyring debian-archive-keyring debootstrap
```

You also need to be in the docker group to use Docker.

```bash
sudo usermod -a -G docker ${USER}
```

Finally you need to login on Docker Hub.

```bash
docker login
```

## Usage

You first need  to choose which dist  between jessie (1.0) and  ascii (2.0) you
want (jessie  will be the  'latest' tag)  and you need  to choose you  user (or
organization) name on Docker Hub.

Show help.

```bash
./build.sh -h
```

Build your own Debian image (eg. jessie).

```bash
./build.sh -d jessie -u vpgrp
```

Build your own Devuan image (eg. jessie) and push it on the Docker Hub.

```bash
./build.sh -d jessie -u vpgrp -p
```

## Limitations

Only work on Debian, Devuan and Ubuntu.

## Development

Please read carefully [CONTRIBUTING.md][contribute-href]  before making a merge
request.

## Miscellaneous

```
    ╚⊙ ⊙╝
  ╚═(███)═╝
 ╚═(███)═╝
╚═(███)═╝
 ╚═(███)═╝
  ╚═(███)═╝
   ╚═(███)═╝
```

[license-img]: https://img.shields.io/badge/license-ISC-blue.svg
[license-href]: LICENSE
[docker-img]: https://img.shields.io/docker/pulls/vptech/devuan.svg
[docker-href]: https://hub.docker.com/r/vptech/devuan
[overview-href]: https://www.devuan.org/
[contribute-href]: CONTRIBUTING.md
