ARG ALFRESCO_TAG
FROM alfresco/alfresco-content-repository-community:${ALFRESCO_TAG}

ARG TOMCAT_DIR=/usr/local/tomcat

USER root

RUN set -x \
    && yum install -y wget \
    && yum install -y unzip

# YourKit
RUN wget https://www.yourkit.com/download/docker/YourKit-JavaProfiler-2019.8-docker.zip -P /tmp/ && \
  unzip /tmp/YourKit-JavaProfiler-2019.8-docker.zip -d /usr/local && \
  rm /tmp/YourKit-JavaProfiler-2019.8-docker.zip

EXPOSE 10001
