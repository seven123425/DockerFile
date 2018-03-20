FROM centos:7

MAINTAINER domybestforyou.tsu@gmail.com

RUN yum install -y wget

RUN wget  --no-check-certificate  \
    -P  /opt/go https://dl.google.com/go/go1.10.linux-amd64.tar.gz

RUN tar zxvf  /opt/go/go1.10.linux-amd64.tar.gz -C /usr/local

RUN yum install -y git

RUN mkdir -p /opt/gopath/go/{src,pkg,bin}


RUN wget -P /opt/glide  https://github.com/Masterminds/glide/releases/download/v0.13.1/glide-v0.13.1-linux-amd64.tar.gz

RUN tar zxvf  /opt/glide/glide-v0.13.1-linux-amd64.tar.gz -C /opt/glide

RUN git clone https://github.com/RayYRC/ScrumMeeting.git \
     /opt/gopath/go/src/ScrumMeeting

ENV GOPATH /opt/gopath/go

ENV PATH /usr/local/go/bin:/opt/glide/linux-amd64:$PATH

RUN cd $GOPATH/src/ScrumMeeting && \
    glide install
