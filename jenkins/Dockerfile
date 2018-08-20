FROM jenkins/jenkins:2.121.2

MAINTAINER Mo Ahmed

ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false"

RUN /usr/local/bin/install-plugins.sh build-with-parameters
RUN /usr/local/bin/install-plugins.sh logstash
RUN /usr/local/bin/install-plugins.sh	pipeline-stage-view
COPY jenkins.plugins.logstash.LogstashConfiguration.xml /var/jenkins_home
