# Dockerizing Storm: Dockerfile for building Storm images
# Based on ubuntu:latest, installs Storm following the instructions from:

# Format: FROM    repository[:version]
FROM jdub/base

# Format: MAINTAINER Name <email@addr.ess>
MAINTAINER Jdub

# Fetch Apache Storm version 0.9.3
RUN wget -q -O - http://mirrors.sonic.net/apache/storm/apache-storm-0.9.3/apache-storm-0.9.3.tar.gz | tar -xzf - -C /opt

# Setup environment
ENV STORM_HOME /opt/apache-storm-0.9.3
RUN groupadd storm; useradd --gid storm --home-dir /home/storm --create-home --shell /bin/bash storm; chown -R storm:storm $STORM_HOME; mkdir /var/log/storm ; chown -R storm:storm /var/log/storm

# Symlink Storm
RUN ln -s $STORM_HOME/bin/storm /usr/bin/storm

# Configure storm
ADD storm.yaml $STORM_HOME/conf/storm.yaml
ADD cluster.xml $STORM_HOME/logback/cluster.xml
ADD config-supervisord.sh /usr/bin/config-supervisord.sh
ADD start-supervisor.sh /usr/bin/start-supervisor.sh 

RUN echo [supervisord] | tee -a /etc/supervisor/supervisord.conf ; echo nodaemon=true | tee -a /etc/supervisor/supervisord.conf

