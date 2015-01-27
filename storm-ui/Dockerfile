# Dockerizing Storm: Storm UI role
# Based on ubuntu:latest, installs Storm following the instructions

# Format: FROM    repository[:version]
FROM jdub/storm

# Format: MAINTAINER Name <email@addr.ess>
MAINTAINER Jdub

RUN /usr/bin/config-supervisord.sh ui

EXPOSE 8080
CMD /usr/bin/start-supervisor.sh