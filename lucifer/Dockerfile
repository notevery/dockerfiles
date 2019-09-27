#以后的每一步操作都是在centos 7系统镜像中进行的操作
FROM centos:7

#申明镜像的制作者
MAINTAINER yangxiaoping <yangxiaoping123@cnpc.com.cn>

#python版本号
ENV PYTHON_VERSION "3.7.1"
#nginx版本号
ENV NGINX_VERSION "1.13.7"

RUN yum update -y \
    && yum -y install wget \
    && wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo \
    && yum clean all \
    && yum makecache \
    && yum -y install gcc automake autoconf libtool make sqlite-devel libffi-devel \
    && yum -y install openssl-devel bzip2-devel expat-devel gdbm-devel readline-devel \
    && yum -y install python-setuptools \
    && easy_install supervisor \
    && cd / \
    #安装python:3.7.1
    && wget https://www.python.org/ftp/python/${PYTHON_VERSION}/Python-${PYTHON_VERSION}.tgz  \
    && tar -zxvf Python-${PYTHON_VERSION}.tgz  \
    && cd Python-${PYTHON_VERSION}  \
    && ./configure --prefix=/usr/local/python3  \
    && make  \
    && make install  \
    && ln -s /usr/local/python3/bin/python3.7 /usr/bin/python3  \
    && ln -s /usr/local/python3/bin/pip3 /usr/bin/pip3  \
    && pip3 install --no-cache-dir --upgrade pip \
    && pip3 install --no-cache-dir virtualenv  \
    && ln -s /usr/local/python3/bin/virtualenv  /usr/bin/virtualenv \
    && pip3 install --no-cache-dir uwsgi  \
    && ln -s /usr/local/python3/bin/uwsgi  /usr/bin/uwsgi \
    && rm -rf /Python-${PYTHON_VERSION}.tgz \
    && rm -rf /Python-${PYTHON_VERSION} \
    #安装nginx:1.13.7
    && cd / \
    && wget http://nginx.org/download/nginx-${NGINX_VERSION}.tar.gz  \
    && tar -zxvf nginx-${NGINX_VERSION}.tar.gz  \
    && cd nginx-${NGINX_VERSION}  \
    && ./configure --prefix=/usr/local/nginx  \
    && make  \
    && make install \
    && rm -rf /nginx-${NGINX_VERSION} \
    && rm -rf /nginx-${NGINX_VERSION}.tar.gz \
    && yum clean all \
    && rm -rf /var/cache/yum
