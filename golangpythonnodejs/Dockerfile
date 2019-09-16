FROM centos:7.6.1810

ENV GOVERSION=1.13 \
    OS=linux \
    ARCH=amd64 \
    GOROOT=/usr/local/go \
    NODEVERSION=10.15.3

# 安装 go
RUN curl -O -s https://dl.google.com/go/go1.13.linux-amd64.tar.gz && \
    tar -C /usr/local -xzf go1.13.linux-amd64.tar.gz && rm -f go1.13.linux-amd64.tar.gz

RUN echo "export GOROOT=/usr/local/go" >> /etc/profile && \
    echo "export PATH=$PATH:$GOROOT/bin" >> /etc/profile

# 安装 nodejs
RUN curl -O -s http://cdn.npm.taobao.org/dist/node/v10.15.3/node-v10.15.3-linux-x64.tar.xz && \
    tar vxf node-v10.15.3-linux-x64.tar.xz -C /usr/ && rm -f node-v10.15.3-linux-x64.tar.xz

RUN ln -s /usr/node-v10.15.3-linux-x64/bin/npm  /usr/local/bin/ && \
    ln -s /usr/node-v10.15.3-linux-x64/bin/node  /usr/local/bin/
