FROM centos
MAINTAINER baron kinju.larzarus@gmail.com
#RUN yum -y update
RUN yum -y install java-1.8.0-openjdk
RUN yum -y install wget
RUN useradd -r tomcat --shell /bin/false
WORKDIR /tmp 
RUN wget http://apache.stu.edu.tw/tomcat/tomcat-8/v8.5.29/bin/apache-tomcat-8.5.29.tar.gz
RUN tar -zxf /tmp/apache-tomcat-8.5.29.tar.gz -C /opt
RUN ln -s /opt/apache-tomcat-8.5.29 /opt/tomcat
RUN rm -rf /opt/apache-tomcat-8.5.29/webapps/docs
RUN rm -rf /opt/apache-tomcat-8.5.29/webapps/host-manager
RUN rm -rf /opt/apache-tomcat-8.5.29/webapps/examples
RUN rm -rf /opt/apache-tomcat-8.5.29/webapps/manager
RUN rm -rf /opt/apache-tomcat-8.5.29/webapps/ROOT
RUN chown -hR tomcat: /opt/tomcat /opt/apache-tomcat-*

ENV CATALINA_HOME /opt/tomcat
ENV PATH $PATH:$CATALINA_HOME/bin

EXPOSE 8080
EXPOSE 8009
VOLUME "/opt/tomcat/webapps"
WORKDIR /opt/tomcat
COPY spring2-mvc-xml-hello-world-1.0-SNAPSHOT.war /opt/tomcat/webapps
CMD ["/opt/tomcat/bin/catalina.sh", "run"]

