FROM phusion/baseimage:latest

MAINTAINER flurdy

ENV DEBIAN_FRONTEND noninteractive

# accept-java-license test commit
RUN echo /usr/bin/debconf shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections

RUN apt-get update && \
  apt-get install -yq python-software-properties && \
  add-apt-repository ppa:webupd8team/java && \
  apt-get remove -yq python-software-properties && \
  apt-get autoremove -yq && \
  apt-get clean -yq && \
  rm -rf /var/lib/apt/lists/*

RUN apt-get update && \
  apt-get install -yq oracle-java6-installer oracle-java6-set-default && \
  apt-get autoremove -yq && \
  apt-get clean -yq && \
  rm -rf /var/lib/apt/lists/*


RUN apt-get update && \
  apt-get install -yq git
  
RUN apt-get update && \
  apt-get install -yq ant  

RUN  echo "    IdentityFile ~/.ssh/id_rsa" >> /etc/ssh/ssh_config
  
RUN chmod 600 /root/.ssh/id_rsa

