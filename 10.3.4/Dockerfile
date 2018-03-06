FROM mariadb:10.3.4
MAINTAINER WPLib Team <team@wplib.org>

COPY container.json /etc/container.json
COPY files /

ENV MYSQL_ALLOW_EMPTY_PASSWORD=yes
ENV MYSQL_DATABASE=wordpress
ENV MYSQL_USER=wordpress
ENV MYSQL_PASSWORD=wordpress

EXPOSE 3306

