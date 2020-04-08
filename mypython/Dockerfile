# #  docker build -t python:myalpine . -f alpineDockerfile
FROM python:alpine

LABEL apk=ustc

ENV MYAPK="mirrors.ustc.edu.cn"

# 更改系统依赖源dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn
RUN sed -i "s/dl-cdn.alpinelinux.org/${MYAPK}/g" /etc/apk/repositories &&\
    apk update

# 更改pip源
RUN mkdir ~/.pip
COPY pip.conf /root/.pip/

ENV TZ="Asia/Shanghai"
