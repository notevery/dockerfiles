# 11.11.174.85:28086/cnpcrd/u14python:3.6.9
FROM 11.11.174.85:28086/cnpcrd/u14python:2.7
# 更新2.7为3.6.9
# /usr/bin/python -> python2.7
# 删除软连接
# rm -rf /usr/bin/python
# python2.7 --> /usr/bin/python2.7
# lrwxrwxrwx 1 root root 9 Dec 21  2013 /usr/bin/python -> python2.7
# 编译之后会生成 /usr/local/bin/python3.6
# 要把 /usr/bin/python -> 指向 python3.6
# ln -s /usr/local/bin/python3.6 /usr/bin/python

WORKDIR /tmp

COPY ./Python-3.6.9.tgz /tmp

RUN tar -xvf ./Python-3.6.9.tgz
WORKDIR /tmp/Python-3.6.9
RUN ./configure && make && make install

RUN rm -rf /usr/bin/python && ln -s /usr/local/bin/python3.6 /usr/bin/python && rm -rf /usr/bin/python-config && ln -s /usr/local/bin/python3.6-config /usr/bin/python-config