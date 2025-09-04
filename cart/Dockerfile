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
    REDIS_HOST="redis" \
    CATALOGUE_HOST="catalogue" \
    CATALOGUE_PORT="8080"
# to start the container and to login    
CMD ["node", "server.js"]    

