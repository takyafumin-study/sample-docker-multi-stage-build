FROM nginx:1.25.3-alpine3.18 AS builder

COPY ./.docker/nginx/templates  /etc/nginx/templates
COPY ./.docker/nginx/nginx.conf /etc/nginx/

FROM builder as dev

FROM builder as prod