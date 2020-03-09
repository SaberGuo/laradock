FROM alpine
LABEL maintainer="Mahmoud Zalt <mahmoud@zalt.me>"

<<<<<<< HEAD
RUN apk add --no-cache beanstalkd

EXPOSE 11300
ENTRYPOINT ["/usr/bin/beanstalkd"]
=======
MAINTAINER Mahmoud Zalt <mahmoud@zalt.me>

ENV DEBIAN_FRONTEND noninteractive
ENV PATH /usr/local/rvm/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

ARG CHANGE_SOURCE=true
#ENV CHANGE_SOURCE ${CHANGE_SOURCE}
RUN if [ ${CHANGE_SOURCE} = true ]; then \
    sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list \
;fi

RUN apt-get update
RUN apt-get install -y beanstalkd
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

VOLUME /var/lib/beanstalkd/data

EXPOSE 11300

CMD ["/usr/bin/beanstalkd"]
>>>>>>> d462adc48c79f6e09641142efbb0f4abfbcbc32d
