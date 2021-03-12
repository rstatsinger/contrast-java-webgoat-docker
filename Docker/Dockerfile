# Dockerfile to run WebGoat 7.1 with Contrast Security
FROM adoptopenjdk/openjdk8:debianslim


# Install WebGoat
# we do not use the WebGoat Docker image because it is based on Debian Jessie which is end of life
ADD https://github.com/WebGoat/WebGoat/releases/download/7.1/webgoat-container-7.1-exec.jar /opt/webgoat/webgoat-container-7.1-exec.jar


# If you are using our Community Edition, this URL is what you need. If you already have a Contrast account or
# you are in a formal evaluation with us, change the resource name (the ce.contrastsecurity.com portion of the URL)
# to reflect your Contrast TeamServer
ENV CONTRAST__API__URL=https://ce.contrastsecurity.com/Contrast


# Install Contrast agent
RUN apt-get update \
  && apt-get install -y gnupg \
  && curl https://pkg.contrastsecurity.com/api/gpg/key/public | apt-key add - \
  && echo "deb https://pkg.contrastsecurity.com/debian-public/ all contrast" > /etc/apt/sources.list.d/contrast-all.list \
  && apt-get update \
  && apt-get install -y contrast-java-agent


# Configure Contrast for WebGoat
ENV CONTRAST__AGENT__JAVA__STANDALONE_APP_NAME=WebGoatDocker \
  CONTRAST__PROTECT__RULES__SQL_INJECTION__DETECT_TAUTOLOGIES=true \
  CONTRAST__SERVER__NAME=WebGoatDockerServer \
  CONTRAST__AGENT__LOGGER__STDERR=true

EXPOSE 8080

CMD ["java","-javaagent:/opt/contrast/contrast-agent.jar","-jar","/opt/webgoat/webgoat-container-7.1-exec.jar"]
