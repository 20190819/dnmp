FROM centos:latest

RUN \
    yum -y install openssl-devel bzip2-devel expat-devel gdbm-devel readline-devel sqlite-devel \
    && yum -y install gcc automake autoconf libtool make wget \
    && yum -y install yum-utils \
    && yum -y install libffi-devel 

RUN mkdir -p /usr/local/python/python3.8 \
    && cd /usr/local/python/python3.8 \
    && curl -O https://www.python.org/ftp/python/3.8.0/Python-3.8.0.tgz \
    && tar -zxf Python-3.8.0.tgz \
    && cd Python-3.8 \
    && ./configure \
    && make && make install 

RUN pip3 install --upgrade pip

RUN mkdir /www/Scrapy -p

WORKDIR /www/Scrapy

ADD ./requirements.txt /www/Scrapy

RUN pip3 install ./requirements.txt

CMD cd /www/Scrapy