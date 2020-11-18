FROM centos:8
RUN dnf -y update

# install leatest nginx & openssl
RUN dnf install -y nginx openssl

# make SSL server certificate
RUN mkdir -p /etc/ssl/private && \
  openssl req -new -newkey rsa:2048 -nodes -out /etc/ssl/private/server.csr -keyout /etc/ssl/private/server.key -subj "/CN=*.lvh.me" && \
  openssl x509 -days 3650 -req -signkey /etc/ssl/private/server.key -in /etc/ssl/private/server.csr -out /etc/ssl/private/server.crt

# nginx config file
COPY ./infra/docker/nginx/default.conf /etc/nginx/conf.d/default.conf

WORKDIR /work/backend
