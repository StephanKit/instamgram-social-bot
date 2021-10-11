# STAGE 1: Compile and Build angular codebase
FROM node:14.18-alpine AS build

WORKDIR /usr/local/app

COPY ./ /usr/local/app

RUN npm install 
RUN npm run build

# STAGE 2: Serve app with nginx server
FROM nginx:latest

COPY --from=build /usr/local/app/dist/front-app /usr/share/nginx/html

EXPOSE 80
