# installing node over official image
#FROM node:20
# minimal official image
FROM node:20-alpine3.21
# creating system user (non root user)
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
#creating the directory to copy the code
WORKDIR /opt/server
# copying the code
COPY package.json .
COPY *.js .
# installing nodejs dependencies
RUN npm install
# giving permission to user
RUN chown -R roboshop:roboshop /opt/server
# environment (systemd) setup
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
# running with non root user
USER roboshop    
# to start the container and to login    
CMD ["node", "server.js"]    