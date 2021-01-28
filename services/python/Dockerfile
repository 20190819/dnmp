FROM centos:7

RUN yum -y install openssl-devel bzip2-devel expat-devel gdbm-devel readline-devel sqlite-devel 
RUN yum -y install gcc automake autoconf libtool make wget 
RUN yum -y install yum-utils 
RUN yum -y install libffi-devel 
RUN yum -y install net-tools
RUN yum -y install vim
RUN yum-builddep -y python

RUN mkdir -p /usr/local/python/python3.8 
WORKDIR /usr/local/python/python3.8
RUN curl -O https://www.python.org/ftp/python/3.8.0/Python-3.8.0.tgz \
    && tar -zxf Python-3.8.0.tgz \
    && cd Python-3.8.0 \
    && ./configure \
    && make && make install 

RUN pip3 install --upgrade pip
RUN mkdir -p /www/Scrapy
WORKDIR /www/Scrapy
ADD ./requirements.txt /www/Scrapy
RUN pip3 install -r ./requirements.txt

WORKDIR /www
# 给这个目录执行权限，x是执行权限
RUN chmod +x /www