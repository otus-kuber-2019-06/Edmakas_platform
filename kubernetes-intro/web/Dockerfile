FROM nginx
RUN groupadd -g 1001 app && \
    useradd -r -u 1001 -g 1001 app && \
    chown 1001:1001 /var/cache/nginx/ -R && \
    touch /var/run/nginx.pid && \
    chown -R 1001:1001 /var/run/nginx.pid && \
    chown -R 1001:1001 /var/cache/nginx && \
    mkdir /app
COPY default.conf /etc/nginx/conf.d/
COPY nginx.conf /etc/nginx/
WORKDIR /app
USER 1001
