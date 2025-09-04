#installing mysql over official image
FROM mysql:8.0 
#mysql password
ENV MYSQL_ROOT_PASSWORD=RoboShop@1
#copping the .js file to this location given by docker
COPY db/* /docker-entrypoint-initdb.d/