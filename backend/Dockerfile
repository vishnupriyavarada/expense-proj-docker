FROM node:20
# Create a directory in container or set a directory
WORKDIR /expense/backend
# copy the code into the above created directory
COPY package.json .
COPY *.js .
# Install dependencies
RUN npm install 
# Create Environment variable to connect to DB
ENV DB_HOST="mysql"
# Command to run the node
CMD ["node", "index.js"]