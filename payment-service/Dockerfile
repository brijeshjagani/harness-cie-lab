FROM tomcat:jre8-openjdk-slim-buster


RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y wget tar

RUN wget -O /tmp/example.txt https://example.com/example.txt


RUN wget -O /tmp/sample.tar.gz https://example.com/sample.tar.gz && \
    tar -xzf /tmp/sample.tar.gz -C /usr/local/bin && \
    rm /tmp/sample.tar.gz
RUN wget -O /tmp/install.sh https://example.com/install.sh && \
    chmod +x /tmp/install.sh && \
    /tmp/install.sh
    


COPY ./payment-service/target/*.jar payment-service.jar

EXPOSE 8080

CMD ["java","-jar","payment-service.jar"]   
