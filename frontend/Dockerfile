FROM nginx:mainline-alpine3.20-slim

RUN rm -rf /etc/nginx/nginx.conf && \
    rm -rf /etc/nginx/conf.d/default.conf && \
    mkdir -p /var/cache/nginx/client_temp && \
    mkdir -p /var/cache/nginx/proxy_temp && \
    mkdir -p /var/cache/nginx/fastcgi_temp && \
    mkdir -p /var/cache/nginx/uwsgi_temp && \
    mkdir -p /var/cache/nginx/scgi_temp && \
    chown -R nginx:nginx /var/cache/nginx && \
    chown -R nginx:nginx /etc/nginx/ && \
    chmod -R 755 /etc/nginx/ && \
    chown -R nginx:nginx /var/log/nginx && \
    touch /var/run/nginx.pid && \
    chown -R nginx:nginx /var/run/nginx.pid /run/nginx.pid
COPY nginx.conf /etc/nginx/nginx.conf
COPY code /usr/share/nginx/html
USER nginx
#COPY expense.conf /etc/nginx/conf.d/expense.conf
# This Dockerfile is setting up an Nginx container with a custom configuration
# (This uses the official Nginx mainline version built on top of the alpine3.20-slim image.
# It provides a lightweight and secure base for Nginx.)
# (This removes the default nginx.conf configuration file and the default server block file (default.conf). 
# This is done because we want to provide custom configuration files instead.)