FROM alpine:3.10

# RUN apk update && \
#     apk add openjdk8
ENV JAVA_HOME="/usr/java" \
    JAVA_VERSION="8" \
    JAVA_HOME=/usr/java/jdk1.8.0_181 \

WORKDIR /tmp

COPY jdk-8u221-linux-x64.tar.gz /tmp
RUN tar vxzf ./jdk-8u181-linux-x64.tar.gz -C /usr/java/

