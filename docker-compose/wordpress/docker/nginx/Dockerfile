FROM nginx:stable-alpine

ADD ./docker/nginx/config/default.conf /etc/nginx/conf.d/default.conf
ADD ./docker/nginx/config/certs /etc/nginx/certs/self-signed

RUN mkdir -p /var/www/html
