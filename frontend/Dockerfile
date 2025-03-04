FROM nginx
# Remove the default nginx index.html
RUN rm -rf /usr/share/nginx/html/index.html
# copy the entire code folder under html folder of user
COPY code /usr/share/nginx/html/
