#FROM nginx
FROM nginx:stable-alpine3.20-perl
# Remove the default nginx index.html
RUN rm -rf /usr/share/nginx/html/index.html
# Remove the container nginx.conf
RUN rm -rf /etc/nginx/nginx.conf
# Remove the default.conf
RUN rm -rf /etc/nginx/conf.d/default.conf

# code added  to create a non root user and 
RUN mkdir -p /var/cache/nginx/client_temp && \
    mkdir -p /var/cache/nginx/proxy_temp && \
    mkdir -p /var/cache/nginx/fastcgi_temp && \
    mkdir -p /var/cache/nginx/uwsgi_temp && \
    mkdir -p /var/cache/nginx/scgi_temp && \
    chown -R nginx:nginx /var/cache/nginx && \
    chown -R nginx:nginx /etc/nginx/ && \
    chmod -R 755 /etc/nginx/ && \
    chown -R nginx:nginx /var/log/nginx

RUN mkdir -p /etc/nginx/ssl/ && \
    chown -R nginx:nginx /etc/nginx/ssl/ && \
    chmod -R 755 /etc/nginx/ssl/

RUN touch /var/run/nginx.pid && \
    chown -R nginx:nginx /var/run/nginx.pid /run/nginx.pid


# Copy our nginx.conf file to the nginx.conf location path
COPY nginx.conf /etc/nginx/nginx.conf
# copy the entire code folder under html folder of user
COPY code /usr/share/nginx/html/
USER nginx
