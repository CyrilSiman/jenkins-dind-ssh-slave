[![Docker Build Status](https://img.shields.io/docker/build/wedroid/jenkins-dind-ssh-slave.svg?style=flat-square)](https://hub.docker.com/r/wedroid/jenkins-dind-ssh-slave/) [![](https://images.microbadger.com/badges/image/wedroid/jenkins-dind-ssh-slave:1.3.svg)](https://microbadger.com/images/wedroid/jenkins-dind-ssh-slave:1.3)

*Directly inspired from [jenkinsci/ssh-slave](https://hub.docker.com/r/jenkinsci/ssh-slave/)* and  [_jenkins/ssh-slave_](https://hub.docker.com/r/jenkins/ssh-slave/)



[How to use this image with Docker Plugin](#how-to-use-this-image-with-docker-plugin)

[Test in Jenkins](#test-in-jenkins)

[Extend this image](#extend-this-image)



# Why this image ?

I used this image as _**FROM**_ for my Jenkins Docker slaves

Compare to ssh-slave this image have some important differences  : 

- this version is based on Alpine instead Debian (~311Mo vs ~658Mo)
- it's a **Docker In Docker** version (you can use Docker inside)  based on official Docker 17.11 DinD image
- Pre-installed : git, subversion, curl, wget



# Jenkins DinD SSH slave Docker image

Available on Docker Hub [wedroid/jenkins-dind-ssh-slave](https://hub.docker.com/r/wedroid/jenkins-dind-ssh-slave/)



### How to use this image with Docker Plugin

To use this image with Jenkins just follow **Launch via SSH** paragraph in this [_page (Docker Plugin)_](https://wiki.jenkins-ci.org/display/JENKINS/Docker+Plugin) and use _wedroid/jenkins-dind-ssh-slave_ instead  _jenkins/ssh-slave_

* This image is made to only works with **Jenkins** ssh user (Jenkins user have right to use Docker without sudo)

  ​

![](https://i.imgur.com/2DQ0tSo.png)



* To run Docker in Docker, the parent container needs to be run with **privileged**. (option available in `Container settings…` menu)



![](https://i.imgur.com/6V9JzNF.png)



### Test in Jenkins

1. In Jenkins, create an item and choose Freestyle project, 

2. Fill  `Restrict where this project can be run` field with the label set in plugin configuration

3. Add a build step, select `Execute shell`and fill field with _/usr/local/bin/docker --version_

   ![](https://i.imgur.com/pnYWveS.png)

4. Save and execute your build

5. After execution, check the console log and search some thing like this

   ```
   + /usr/local/bin/docker --version
   Docker version 17.10.0-ce, build f4ffd25
   ```




### Extend this image

 ([sample with Node](https://github.com/CyrilSiman/jenkins-dind-ssh-slave-node)) 
