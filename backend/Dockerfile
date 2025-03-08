# FROM node:20 - Replacing the base image with node:20.18.3-alpine3.21. as alpine is the smallest OS and 
                 # can reduce the size of the image
FROM node:20.18.3-alpine3.21
# Create a directory in container or set a directory
WORKDIR /opt/backend
# copy the code into the above created directory
COPY package.json .
COPY *.js .
# Install dependencies
RUN npm install 
# Create Environment variable to connect to DB. Give the mysql container name else backend will not be able to connect to mysql
ENV DB_HOST="mysql"
#ENV DB_HOST="localhost" # used when using host network
# Command to run the node
CMD ["node", "index.js"]