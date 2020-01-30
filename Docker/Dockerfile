# Dockerfile to run WebGoat 7.1 with Contrast Security Community Edition

FROM anapsix/alpine-java:jdk8

# TODO Edit the following three lines and substitute the keys from your Contrast Security Your Account page

ENV OrgID=<Replace with your Organization ID>

ENV Auth=<Replace with your Authorization Header>

ENV APIKey=<Replace with your API Key>

# uncomment one of the following lines, depending if you're in an Eval POC, or using Community Edition

# ENV CONTRAST__BASEURL=https://ce.contrastsecurity.com/Contrast/api/ng/$OrgID
# ENV CONTRAST__BASEURL=https://eval.contrastsecurity.com/Contrast/api/ng/$OrgID

# End TODO

RUN mkdir /opt/app
RUN mkdir /opt/contrast

RUN apk update && apk add ca-certificates && update-ca-certificates && apk add openssl
RUN apk update; apk add curl
RUN wget https://github.com/WebGoat/WebGoat/releases/download/7.1/webgoat-container-7.1-exec.jar -O /opt/app/webgoat.jar

RUN curl --max-time 10 $CONTRAST__BASEURL/agents/default/JAVA?jvm=1_5 -H API-Key:$APIKey -H Authorization:$Auth -o /opt/contrast/contrast.jar

EXPOSE 8080

CMD ["java","-javaagent:/opt/contrast/contrast.jar","-Dcontrast.standalone.appname=WebGoatDocker","-Dcontrast.server=DockerServer","-jar","/opt/app/webgoat.jar"]
