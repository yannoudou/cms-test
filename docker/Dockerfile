FROM tomcat:9-jdk11

RUN mkdir -p /opt/magnolia
VOLUME /opt/magnolia

COPY tomcat/server.xml $CATALINA_HOME/conf/server.xml
COPY coutest-cms*.war $CATALINA_HOME/webapps/ROOT.war

HEALTHCHECK --interval=1m --timeout=5s --retries=5 \
  CMD curl --fail http://localhost:8080/.rest/status || exit 1