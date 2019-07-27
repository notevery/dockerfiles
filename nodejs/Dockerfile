FROM node:11.7.0-alpine
LABEL maintainer "Bitnami <leaderjs@live.com>"

# chromedriver
ENV CR_5 2.46

# node_sass 
ENV NS_5 4.9.0

# ENV NS_A 4.11.0

RUN mkdir /tmp/${CR_5} \
    mkdir /tmp/${NS_5}

# mkdir /tmp/${NS_A}

# 为什么不解压？？？ nodejs version 11.7 对应 node module 为 67
ADD http://cdn.npm.taobao.org/dist/chromedriver/2.46/chromedriver_linux64.zip /tmp
ADD https://github.com/sass/node-sass/releases/download/v4.11.0/linux-x64-67_binding.node /tmp/
# ADD https://github.com/sass/node-sass/releases/download/${NS_A}/linux-x64-47_binding.node /tmp/${NS_A}
# ADD https://github.com/sass/node-sass/releases/download/${NS_5}/linux-x64-47_binding.node /tmp/${NS_5}