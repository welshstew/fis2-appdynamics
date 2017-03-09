FROM registry.access.redhat.com/jboss-fuse-6/fis-java-openshift:latest

USER root

ADD appdynamics/ /opt/appdynamics/
COPY usr/local/bin/ /usr/local/bin/

RUN chmod 775 /usr/local/bin/* /opt/run-java/run-java.sh /opt/run-java/java-default-options /opt/run-java/container-limits /opt/run-java/debug-options \
  && /usr/local/bin/fix-permissions.sh /usr/local/bin \
  && /usr/local/bin/fix-permissions.sh /opt/appdynamics \
  && chown -R jboss:jboss /opt/appdynamics

#jboss from FIS
USER 185
