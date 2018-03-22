 FROM centos:centos7
 MAINTAINER dylan

 # Install prepare infrastructure
 RUN yum -y update && \
  yum -y install wget && \
  yum -y install tar

 # Prepare environment
   ENV JAVA_HOME /opt/java
   ENV CATALINA_HOME /opt/tomcat
   ENV PATH $PATH:$JAVA_HOME/bin:$CATALINA_HOME/bin:$CATALINA_HOME/scripts

 # Install Oracle Java8
   ENV JAVA_VERSION 8u162
   ENV JAVA_BUILD 8u162-b12
   ENV JAVA_DL_HASH 0da788060d494f5095bf8624735fa2f1

   RUN wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" \
    http://download.oracle.com/otn-pub/java/jdk/${JAVA_BUILD}/${JAVA_DL_HASH}/jdk-${JAVA_VERSION}-linux-x64.tar.gz && \
    tar -xvf jdk-${JAVA_VERSION}-linux-x64.tar.gz && \
    rm jdk*.tar.gz && \
    mv jdk* ${JAVA_HOME}


 # Install Tomcat

   RUN wget http://ftp.twaren.net/Unix/Web/apache/tomcat/tomcat-8/v8.5.29/bin/apache-tomcat-8.5.29.tar.gz && \
       tar -xvf apache-tomcat-8.5.29.tar.gz && \
       rm apache-tomcat*.tar.gz && \
       mv apache-tomcat* ${CATALINA_HOME}

   RUN chmod +x ${CATALINA_HOME}/bin/*sh
   EXPOSE 8080
   CMD ["opt/tomcat/bin/catalina.sh","run"]
