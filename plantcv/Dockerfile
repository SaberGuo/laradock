FROM ubuntu:16.04

#FROM python:3-alpine

#RUN mkdir -p /usr/src/plantcv_app
#WORKDIR /usr/src/plantcv_app

#COPY plantcv_server.py /usr/src/plantcv_app/

#RUN apk update && apk add \
#    libuuid \
#    pcre \
#    mailcap \
#    gcc \
#    libc-dev \
#    linux-headers \
#    pcre-dev \
#    && pip3 install --no-cache-dir -r requirements.txt -i http://mirrors.aliyun.com/pypi/simple/ \
#    && apk del \
#    gcc \
#    libc-dev \
#    linux-headers \
#    && rm -rf /tmp/*

#EXPOSE 9876

#CMD ["python3", "plantcv_server.py"]

## 更改配置源
RUN mv /etc/apt/sources.list /etc/apt/sources-bak.list
COPY sources.list /etc/apt/sources.list

RUN apt-get update \
    && apt-get install software-properties-common -y

RUN add-apt-repository ppa:jonathonf/python-3.6 \
    && apt-get update

RUN apt-get install -y vim \
    && apt-get install -y curl\
    #&& apt-get install -y openssl\
    #&& apt-get install -y libssl-dev\
    #&& apt-get install -y libc6-dev gcc\
    #&& apt-get install -y make build-essential zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm tk-dev\
    && apt-get install -y python3.6 \
    && curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py\
    && python3.6 get-pip.py
    #&& apt-get install -y python3-pip \
    #&& apt-get install -y python-pip python-dev build-essential
WORKDIR /var/www
ADD requirements.txt ./
RUN pip3 install opencv-python && pip3 install --no-cache-dir -r requirements.txt                  


CMD ["bash"]
