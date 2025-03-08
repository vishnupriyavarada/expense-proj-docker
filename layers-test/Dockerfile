# FROM node:20 - Replacing the base image with node:20.18.3-alpine3.21. as alpine is the smallest OS and 
                 # can reduce the size of the image
FROM node:20.18.3-alpine3.21
# Creating expense user
RUN addgroup -S expense && adduser -S expense -G expense 
RUN mkdir /opt/backend
# Now hand over '/opt/backend' directory permissions to expense user
RUN chown -R expense:expense /opt/backend
# Create a directory in container or set a directory
    # Now whatever files comes into /opt/backend  directory it from expense user
WORKDIR /opt/backend
# copy the code into the above created directory
COPY package.json .
COPY *.js ./
# Install dependencies
RUN npm install 
# Create Environment variable to connect to DB. Give the mysql container name else backend will not be able to connect to mysql
ENV DB_HOST="mysql"
#ENV DB_HOST="localhost" # used when using host network
# now the container runs with non root user expense rather than root user
USER expense
# Command to run the node
CMD ["node", "index.js"]