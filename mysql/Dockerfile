FROM mysql:9
ENV MYSQL_ROOT_PASSWORD=RoboShop@1 \
    MYSQL_DATABASE=cities \
    MYSQL_USER=shipping \
    MYSQL_PASSWORD=RoboShop@1
COPY scripts/* /docker-entrypoint-initdb.d/
# EXPOSE 3306
# CMD ["mysqld"]