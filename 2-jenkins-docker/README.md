# How to use it
### 1. Download this folder
```bash
$ git clone https://github.com/seyslee/jenkins-pipeline-toyproject
```
<br>

### 2. Move to Dockerfile
```bash
$ ls
demolab  jenkins-docker  snap
```
<br>

```bash
$ mv jenkins-docker
```
<br>

### 3. Build
```bash
$ docker build -t jenkins-docker .
Sending build context to Docker daemon  91.14kB
Step 1/4 : FROM jenkins/jenkins:lts
 ---> 2a4bbe50c40b
Step 2/4 : USER root
 ---> Running in 704296feaa43
Removing intermediate container 704296feaa43
 ---> 039287e2e8ac
Step 3/4 : RUN mkdir -p /tmp/download &&  curl -L https://download.docker.com/linux/static/stable/x86_64/docker-18.03.1-ce.tgz | tar -xz -C /tmp/download &&  rm -rf /tmp/download/docker/dockerd &&  mv /tmp/download/docker/docker* /usr/local/bin/ &&  rm -rf /tmp/download &&  groupadd -g 999 docker &&  usermod -aG staff,docker jenkins
 ---> Running in 9ad8d920378a
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 36.9M  100 36.9M    0     0  9511k      0  0:00:03  0:00:03 --:--:-- 9509k
Removing intermediate container 9ad8d920378a
 ---> ac00a7709991
Step 4/4 : USER jenkins
 ---> Running in 79cfb5613b22
Removing intermediate container 79cfb5613b22
 ---> 0bd92a6415d2
Successfully built 0bd92a6415d2
Successfully tagged jenkins-docker:latest
```
<br>

### 4. Run
```bash
$ docker run -p 8080:8080 -p 50000:50000 -v /var/jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock --name jenkins -d jenkins-docker
```
