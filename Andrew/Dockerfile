FROM centos

MAINTAINER Andrew andrewlin019@gmail.com

RUN yum -y update
RUN yum -y install wget
RUN yum -y install java-1.8.0-openjdk.x86_64

RUN cd /tmp
RUN wget http://apache.stu.edu.tw/tomcat/tomcat-8/v8.5.29/bin/apache-tomcat-8.5.29.tar.gz

RUN tar -zxvf apache-tomcat-8.5.29.tar.gz
RUN mv apache-tomcat-8.5.29 /opt/

RUN rm -rf /opt/apache-tomcat-8.5.29/webapps/ROOT
RUN mkdir /opt/apache-tomcat-8.5.29/webapps/ROOT

RUN echo "<html>Hello World</html>" >> /opt/apache-tomcat-8.5.29/webapps/ROOT/index.html

EXPOSE 8080

RUN cd /opt/apache-tomcat-8.5.29/bin/

CMD ["/opt/apache-tomcat-8.5.29/bin/catalina.sh", "run"]
