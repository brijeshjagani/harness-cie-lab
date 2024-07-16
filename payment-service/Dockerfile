FROM tomcat:jre8-openjdk-slim-buster


RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y wget tar
RUN apt-get install -y wget unzip


RUN wget -O /tmp/node-v14.17.0-linux-x64.tar.xz https://nodejs.org/dist/v14.17.0/node-v14.17.0-linux-x64.tar.xz && \
    mkdir -p /usr/local/lib/nodejs && \
    tar -xJf /tmp/node-v14.17.0-linux-x64.tar.xz -C /usr/local/lib/nodejs && \
    rm /tmp/node-v14.17.0-linux-x64.tar.xz
    
RUN wget -O /tmp/terraform.zip https://releases.hashicorp.com/terraform/1.0.0/terraform_1.0.0_linux_amd64.zip && \
    unzip /tmp/terraform.zip -d /usr/local/bin && \
    rm /tmp/terraform.zip

COPY ./payment-service/target/*.jar payment-service.jar

EXPOSE 8080

CMD ["java","-jar","payment-service.jar"]   
