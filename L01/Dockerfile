#stage 1 - build stage 
FROM node:22-alpine AS builder

WORKDIR  /app

COPY package*.json ./

RUN npm install

COPY server.js .

#SATAGE 2 PRODUCTION STAGE 
FROM  node:22-alpine 

WORKDIR  /app

COPY --from=builder /app .

EXPOSE 3000

RUN ["npm", "start"]

