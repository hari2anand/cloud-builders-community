FROM java:8
ARG version=1.16.1

RUN apt-get update \
 && DEBIAN_FRONTEND=noninteractive \
  apt-get install -y ca-certificates curl wget build-essential
RUN apt-get install -y maven
RUN apt-get -y update && \
    apt-get -y install \
        apt-transport-https \
        ca-certificates \
        curl \
        make \
        gnupg2 \
        software-properties-common && \
    curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - && \
    apt-key fingerprint 0EBFCD88 && \
    add-apt-repository \
       "deb [arch=amd64] https://download.docker.com/linux/debian \
       $(lsb_release -cs) \
       edge" && \
    apt-get -y update && \
    apt-get -y install docker-ce
RUN \
   apt-get -y update && \
   apt-get -y install ca-certificates curl && \
   curl -L "https://github.com/docker/compose/releases/download/$version/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && \
   chmod +x /usr/local/bin/docker-compose


ENTRYPOINT ["make"]