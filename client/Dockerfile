# Pull the base image
FROM node:18-alpine

RUN mkdir /app
WORKDIR /app

# Copy app dependencies to container
COPY package*.json ./
RUN npm i

COPY public public
COPY src src

# Deploy app for local development
CMD npm start