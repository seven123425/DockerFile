FROM centos:7

MAINTAINER domybestforyou.tsu@gmail.com

RUN yum install -y wget

RUN wget  --no-check-certificate  \
    -P  /opt/go https://dl.google.com/go/go1.10.linux-amd64.tar.gz

RUN tar zxvf  /opt/go/go1.10.linux-amd64.tar.gz -C /opt/go

RUN yum install -y git

RUN mkdir -p /opt/gopath/go

RUN git clone https://github.com/RayYRC/ScrumMeeting.git \
     /opt/path/go/ScrumMeeting
