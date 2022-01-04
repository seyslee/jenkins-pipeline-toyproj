# Overview
Code repository used for CI/CD pipeline for toy project.    

I use Jenkins the DevOps way.  
Automate Jenkins jobs by using Jenkins Pipelines, Github, Docker, and the Jenkins Job DSL.
<br>

# Environment
- **Cloud Platform** : DigitalOcean
- **Virtual Server** (In DigitalOcean, a virtual server is called a droplet.)
  - **OS** : Ubuntu 20.04.3 LTS
  - **Docker** : Docker version 20.10.12, build e91ed57
  - **Container Image** : jenkins/jenkins:lts
  - **Jenkins 2.319.1** (Deployed as a docker container)
  - **Ports** : 8080(Jenkins web), 50000(Jenkins Slave)
<br>

### What i did
**Integrated Jenkins Pipeline with** ...
- Docker
- Docker Hub Container Image Library
- Github
- Slack +Inbound Webhooks
- Gradle
<br>

**To do**
- JFrog Artifactory
- SonarQube
<br>

# Reference
This project references Udemy's "Learn DevOps: CI/CD with Jenkins using Pipelines and Docker" course.
