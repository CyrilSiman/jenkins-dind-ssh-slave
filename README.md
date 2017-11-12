*Directly inspired from [jenkinsci/ssh-slave](https://hub.docker.com/r/jenkinsci/ssh-slave/)* and  [_jenkins/ssh-slave_](https://hub.docker.com/r/jenkins/ssh-slave/)

# Why this image ?

There is some important differences compare to ssh-slave image : 

- this version is based on Alpine instead Debian
- it's a **Docker In Docker** version (you can use Docker inside)  based on official Docker DinD image

# Jenkins DinD SSH slave Docker image

Available on Docker Hub [wedroid/jenkins-dind-ssh-slave](https://hub.docker.com/r/wedroid/jenkins-dind-ssh-slave/)



### How to use this image with Docker Plugin

To use this image with Jenkins just follow **Launch via SSH** paragraph in this [_page (Docker Plugin)_](https://wiki.jenkins-ci.org/display/JENKINS/Docker+Plugin) and use _wedroid/jenkins-dind-ssh-slave_ instead  _jenkins/ssh-slave_



![](https://i.imgur.com/42hFzyk.png)



### Where is Docker ?

Docker bin is available in **/usr/local/bin**



~~For convenience, I suggest you to add an environment variable in Node properties~~ Environement variables aren't correctly save.   [Issue open](https://github.com/jenkinsci/docker-plugin/issues/553)

![](https://i.imgur.com/4cO8Kp5.png)



### Test

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

