---
title: Requirements
---

#### Daemon Requirements

!!!! The daemon requires Docker and NodeJS to run.


##### Docker Setup
###### Install yum-utils
```
sudo yum install -y yum-utils
```

###### Add Docker repo
```
yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo \
    && yum makecache fast
```

###### Install Docker
```
yum install docker-ce
```
##### NodeJS Setup
###### Install EPEL repo
```
yum install epel-release
```

###### Install NodeJS
```
yum install nodejs
```