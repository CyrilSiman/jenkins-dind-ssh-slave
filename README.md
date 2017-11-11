*Directly inspired from [jenkinsci/ssh-slave](https://hub.docker.com/r/jenkinsci/ssh-slave/)* and  [_jenkins/ssh-slave_](https://hub.docker.com/r/jenkins/ssh-slave/)

# Why a new version ?

There are some differences : 

- this version is based on Alpine instead Debian
- it's a **Docker In Docker** version (you can use Docker inside)  based on official Docker DinD image

# Jenkins DinD SSH slave Docker image

Available on Docker Hub [wedroid/jenkins-dind-ssh-slave](https://hub.docker.com/r/wedroid/jenkins-dind-ssh-slave/)



### How to use this image with Docker Plugin

To use this image with Jenkins just follow **Launch via SSH** paragraph in this [_page (Docker Plugin)_](https://wiki.jenkins-ci.org/display/JENKINS/Docker+Plugin) and use _wedroid/jenkins-dind-ssh-slave_ instead  _jenkins/ssh-slave_

