# Dockerfile to run WebGoat 7.1 with Contrast Security

FROM anapsix/alpine-java:jdk8

# TODO Edit the following 3 lines and substitute the keys from your Contrast Security Your Account page

ENV OrgID=<Replace with your Organization ID>

ENV Auth=<Replace with your Authorization Header>

ENV APIKey=<Replace with your API Key>

# End TODO

# If you are using our Community Edition, this URL is what you need. If you already have a Contrast account or
# you are in a formal evaluation with us, change the resource name (the ce.contrastsecurity.com portion of the URL)
# to reflect your Contrast TeamServer

ENV CONTRAST__BASEURL=https://ce.contrastsecurity.com/Contrast/api/ng/$OrgID

RUN mkdir /opt/app
RUN mkdir /opt/contrast

RUN apk update && apk add ca-certificates && update-ca-certificates && apk add openssl
RUN apk update; apk add curl
RUN wget https://github.com/WebGoat/WebGoat/releases/download/7.1/webgoat-container-7.1-exec.jar -O /opt/app/webgoat.jar

RUN curl --max-time 20 $CONTRAST__BASEURL/agents/default/JAVA -H API-Key:$APIKey -H Authorization:$Auth -o /opt/contrast/contrast.jar

EXPOSE 8080

CMD ["java","-javaagent:/opt/contrast/contrast.jar","-Dcontrast.standalone.appname=WebGoatDocker","-Dcontrast.protect.rules.sql-injection.detect_tautologies=true","-Dcontrast.server=WebGoatDockerServer","-jar","/opt/app/webgoat.jar"]
