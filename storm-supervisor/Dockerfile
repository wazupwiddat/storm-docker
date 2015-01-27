# Dockerizing Storm: Supervisor role
# Based on ubuntu:latest, installs Storm following the instructions

# Format: FROM    repository[:version]
FROM jdub/storm

# Format: MAINTAINER Name <email@addr.ess>
MAINTAINER Jdub

EXPOSE 6700
EXPOSE 6701
EXPOSE 6702
EXPOSE 6703
EXPOSE 8000

RUN /usr/bin/config-supervisord.sh supervisor
RUN /usr/bin/config-supervisord.sh logviewer
CMD /usr/bin/start-supervisor.sh