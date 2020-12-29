
FROM ubuntu:latest

RUN apt update && apt install  openssh-server sudo -y

RUN apt-get install -y apache2

RUN apt-get install -y apache2-utils

RUN mkdir --mode=700 /root/.ssh/

COPY docker_key /root/.ssh/

RUN chmod 600 /root/.ssh/docker_key

EXPOSE 80
EXPOSE 22

CMD service sshd start & apache2ctl -D FOREGROUND
