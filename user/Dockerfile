#installing node over official image
FROM node:20
#creating the directory to copy the code
WORKDIR /opt/server
# copying the code
COPY package.json .
COPY *.js .
# installing nodejs dependencies
RUN npm install
# environment (systemd) setup
ENV MONGO="true" \
    REDIS_URL="redis://redis:6379" \
    MONGO_URL="mongodb://mongodb:27017/users"
# to start the container and to login    
CMD ["node", "server.js"]    