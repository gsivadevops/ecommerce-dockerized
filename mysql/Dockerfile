# #installing mysql over official image
# FROM mysql:8.0 
# #mysql password
# ENV MYSQL_ROOT_PASSWORD=RoboShop@1
# #copping the .js file to this location given by docker
# COPY db/* /docker-entrypoint-initdb.d/

# To access the password fron secret manager by setting it as env variable in entrypoint.sh 
FROM mysql:8.0
COPY db/* /docker-entrypoint-initdb.d/
COPY entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh
ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]