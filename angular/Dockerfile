FROM node:10 AS build

LABEL maintainer="antoine"

WORKDIR /app

COPY . .

RUN npm install

RUN npm run build

FROM nginx:1.27-alpine

COPY --from=build /app/dist/ /usr/share/nginx/html

COPY nginx/ /etc/nginx

COPY entrypoint.sh /docker-entrypoint.d/entrypoint.sh
