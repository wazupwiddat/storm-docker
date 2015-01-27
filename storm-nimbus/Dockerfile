# Dockerizing Storm: Numbus role
# Based on ubuntu:latest, installs Storm following the instructions

# Format: FROM    repository[:version]
FROM jdub/storm

# Format: MAINTAINER Name <email@addr.ess>
MAINTAINER Jdub

RUN /usr/bin/config-supervisord.sh nimbus 
RUN /usr/bin/config-supervisord.sh drpc

EXPOSE 6627
EXPOSE 3772
EXPOSE 3773
ADD start-supervisor.sh /usr/bin/start-supervisor.sh
CMD /usr/bin/start-supervisor.sh