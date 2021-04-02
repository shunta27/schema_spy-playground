FROM openjdk:8u121-jdk-alpine

ENV POSTGRESL_DRIVER_URL https://jdbc.postgresql.org/download/postgresql-42.2.18.jar
ENV MYSQL_DRIVER_URL https://repo1.maven.org/maven2/mysql/mysql-connector-java/8.0.23/mysql-connector-java-8.0.23.jar
ENV APP_URL https://github.com/schemaspy/schemaspy/releases/download/v6.1.0/schemaspy-6.1.0.jar

WORKDIR /app

RUN apk --update add graphviz ttf-dejavu && \
    apk --update add --virtual .builddep tzdata wget libressl && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    wget -O postgresql-42.2.18.jar ${POSTGRESL_DRIVER_URL} && \
    wget -O mysql-connector-java-8.0.23.jar ${MYSQL_DRIVER_URL} && \
    wget -O schemaspy.jar ${APP_URL} && \
    apk del .builddep && \
    rm -rf /var/cache/apk/*
