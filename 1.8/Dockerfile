FROM alpine:3.3

ENV NGINX_VERSION 1.8.1

RUN apk update && \
    apk add 'nginx<1.8.2' && \
    mkdir -p /etc/nginx/sites-enabled /etc/nginx/sites-available && \
    ln -sf /dev/stdout /var/log/nginx/access.log && \
    ln -sf /dev/stderr /var/log/nginx/error.log && \
    rm -rf /var/cache/apk/*

COPY ./nginx.conf /etc/nginx/nginx.conf

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
