FROM debian:stretch

RUN apt update && apt upgrade -y
RUN apt install nginx-light

COPY default.conf /etc/nginx/sites-available/default

EXPOSE 80
CMD nginx -g daemon off;
