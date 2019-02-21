FROM java:8

RUN apt-get update \
 && DEBIAN_FRONTEND=noninteractive \
  apt-get install -y ca-certificates curl wget build-essential
RUN apt-get install -y maven

ENTRYPOINT ["make"]