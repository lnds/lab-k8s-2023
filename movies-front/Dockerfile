FROM node:20.5-alpine3.17 as build-stage

WORKDIR /usr/app

COPY package.json .

RUN npm install --quiet

COPY . .

RUN npm run build

FROM nginx:stable-alpine

COPY build/ /usr/share/nginx/html
