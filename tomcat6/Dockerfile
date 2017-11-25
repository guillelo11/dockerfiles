FROM andreptb/oracle-java:6-alpine

RUN apk --no-cache add curl && curl https://archive.apache.org/dist/tomcat/tomcat-6/v6.0.14/bin/apache-tomcat-6.0.14.tar.gz -o /tmp/apache-tomcat-6.0.14

RUN cd /usr/local && \
    tar xzf /tmp/apache-tomcat-6.0.14 -C ./ && \
    ln -s ./apache-tomcat-6.0.14 ./tomcat && \
    rm -rf /usr/local/tomcat/webapps

ENV CATALINA_HOME /usr/local/tomcat

EXPOSE 8080
EXPOSE 8000

CMD ["/usr/local/tomcat/bin/catalina.sh", "jpda","run"]