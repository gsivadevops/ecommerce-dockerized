#installing maven with java over official image
FROM maven
#creating the directory to copy the code
WORKDIR /opt/server
# copying the code
COPY pom.xml .
COPY src /opt/server
# installing maven dependencies
RUN mvn clean 
# moving the created jar - shipping-1.0.jar, form target folder to /opt/server with shipping.jar
mv /opt/server/target/shipping-1.0.jar /opt/server/shipping.jar
# environment (systemd) setup
ENV MONGO="true" \
    CART_ENDPOINT="cart:8080"
    DB_HOST="mysql"
# to start the container and to login    
CMD ["java", "-jar", "shipping.jar"]    