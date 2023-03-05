# Base image
FROM jenkins/jenkins:lts

# Disable setup wizard
ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false"

# # Copy plugins file to container
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt

# # Install plugins
# RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt

RUN jenkins-plugin-cli -f /usr/share/jenkins/ref/plugins.txt

# Set admin user
ENV JENKINS_USER admin
ENV JENKINS_PASS admin

# Skip initial setup
ENV JAVA_OPTS="${JAVA_OPTS} -Djenkins.install.runSetupWizard=false"

# Expose Jenkins port
EXPOSE 8080

# # Copy default Jenkins config file
# COPY config.xml /usr/share/jenkins/ref/config.xml
