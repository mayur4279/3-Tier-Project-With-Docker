FROM mysql:latest

ENV MYSQL_ROOT_PASSWORD=12345678

ADD https://raw.githubusercontent.com/mayur4279/tmp/main/student.sql /docker-entrypoint-initdb.d/

RUN chmod 644 /docker-entrypoint-initdb.d/student.sql

EXPOSE 3306
