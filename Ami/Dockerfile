FROM centos:7

MAINTAINER domybestforyou.tsu@gmail.com

RUN mkdir -p /root/go/{src,pkg,bin}

ENV GOPATH /root/go
 
ENV PATH /usr/local/go/bin:$GOPATH/bin:$PATH

RUN yum install -y wget

RUN wget  --no-check-certificate  \
    -P  /opt/go https://dl.google.com/go/go1.10.linux-amd64.tar.gz

RUN tar zxvf  /opt/go/go1.10.linux-amd64.tar.gz -C /usr/local

RUN yum install -y git

RUN go get -u github.com/Masterminds/glide

RUN git clone https://github.com/RayYRC/ScrumMeeting.git \
    $GOPATH/ScrumMeeting

RUN cd $GOPATH/src/ScrumMeeting && \
    glide install

CMD cd $GOPATH/src/ScrumMeeting && go run main.go
