FROM mysql:latest

ENV MYSQL_ROOT_PASSWORD=<yourpw>
ENV MYSQL_DATABASE=<yourdb>
# Initialization script for MySQLDB, I usually put here the DB dump.
COPY dump.sql /docker-entrypoint-initdb.d/dump.sql

EXPOSE 3306
