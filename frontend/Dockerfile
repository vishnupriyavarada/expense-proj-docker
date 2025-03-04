FROM nginx
# Remove the default nginx index.html
RUN rm -rf /usr/share/nginx/html/index.html
# Remove the container nginx.conf
RUN rm -rf /etc/nginx/nginx.conf
# Copy our nginx.conf file to the nginx.conf location path
COPY nginx.conf /etc/nginx/nginx.conf
# copy the entire code folder under html folder of user
COPY code /usr/share/nginx/html/
