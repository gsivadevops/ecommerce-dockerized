# multistage builds
FROM node:20-alpine3.21 AS builder
WORKDIR /opt/server
# install build dependencies
COPY package.json .
COPY *.js .
RUN npm install

FROM node:20-alpine3.21
# creating system user (non root user)
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
# environment (systemd) setup
ENV MONGO="true" \
    REDIS_URL="redis://redis:6379" \
    MONGO_URL="mongodb://mongodb:27017/users"
WORKDIR /opt/server
# running with non root user
USER roboshop
# copying the installed packages from builder
COPY --from=builder /opt/server /opt/server
CMD ["node","server.js"]

# #installing node over official image
# FROM node:20
# #creating the directory to copy the code
# WORKDIR /opt/server
# # copying the code
# COPY package.json .
# COPY *.js .
# # installing nodejs dependencies
# RUN npm install
# # environment (systemd) setup
# ENV MONGO="true" \
#     REDIS_URL="redis://redis:6379" \
#     MONGO_URL="mongodb://mongodb:27017/users"
# # to start the container and to login    
# CMD ["node", "server.js"]    

