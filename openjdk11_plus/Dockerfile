FROM adoptopenjdk/openjdk11:alpine-jre

ARG FILEBEAT_VERSION=6.7.1
ENV FILEBEAT_VERSION ${FILEBEAT_VERSION}
ARG FILEBEAT_NAME=filebeat-${FILEBEAT_VERSION}-linux-x86_64
ARG FILEBEAT_URL=https://artifacts.elastic.co/downloads/beats/filebeat/${FILEBEAT_NAME}.tar.gz

RUN apk update \
    && apk add busybox-extras \
    && apk add curl

RUN cd /tmp \
    && curl -s ${FILEBEAT_URL} | tar zx -C /opt \
    && ln -s /opt/${FILEBEAT_NAME} /opt/filebeat \
    && ln -s /opt/filebeat/filebeat /bin/filebeat
