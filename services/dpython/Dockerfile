FROM ubuntu:latest
RUN apt-get install -y openssh-server \
    apt-get install -y python3.8 python3-pip \
    apt-get install -y zlib1g-dev libffi-dev libssl-dev \
    apt-get install -y libxml2-dev libxslt1-dev 
RUN mkdir /www/Scrapy
WORKDIR /www/Scrapy
ADD ./requirements.txt /www/Scrapy
RUN pip3 install -r ./requirements.txt 