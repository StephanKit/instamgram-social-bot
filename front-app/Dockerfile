#https://typeofnan.dev/how-to-serve-an-angular-app-with-nginx-in-docker/
FROM node:14 AS builder

WORKDIR /app

COPY . .

RUN npm i & npm run build

# # # STAGE 2: Serve app with nginx server
FROM nginx:alpine

WORKDIR /usr/share/nginx/html

RUN rm -rf ./*

COPY --from=builder /app/dist/front-app .

ENTRYPOINT ["nginx", "-g", "daemon off;"]



