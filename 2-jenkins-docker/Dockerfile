FROM jenkins/jenkins:lts
USER root
ARG docker_gid=998
# Hint:
# Make sure to change the "docker_gid" with the GID(Group ID) your docker group has on your system.
# To check run:
# cat /etc/group | grep docker
# to find the gid of docker on your system.

RUN mkdir -p /tmp/download && \
 curl -L https://download.docker.com/linux/static/stable/x86_64/docker-18.03.1-ce.tgz | tar -xz -C /tmp/download && \
 rm -rf /tmp/download/docker/dockerd && \
 mv /tmp/download/docker/docker* /usr/local/bin/ && \
 rm -rf /tmp/download && \
 groupadd -g {docker_gid} docker && \
 usermod -aG staff,docker jenkins

USER jenkins
