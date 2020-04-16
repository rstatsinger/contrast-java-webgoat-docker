# Dockerfile to run WebGoat 7.1 with Contrast Security

FROM anapsix/alpine-java:jdk8

# TODO Edit the following 3 lines and substitute the keys from your Contrast Security Your Account page

ENV OrgID=<Replace with your Organization ID>

ENV Auth=<Replace with your Authorization Header>

ENV APIKey=<Replace with your API Key>

# TODO Add your initials to tbe begining or end of the AppName

ENV AppName=WebGoatDocker

# TODO Uncomment one of the following lines, depending on whether you have an existing account 
# in our Eval environment, or are using Community Edition

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

CMD ["java","-javaagent:/opt/contrast/contrast.jar","-Dcontrast.standalone.appname=$AppName","-Dcontrast.server=$AppNameServer","-jar","/opt/app/webgoat.jar"]
