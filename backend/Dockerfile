FROM node:20
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