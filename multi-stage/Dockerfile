# Build - 1st docker file
FROM node:20.18.3-alpine3.21 as build
RUN mkdir /opt/backend
WORKDIR /opt/backend
COPY package.json .
COPY *.js ./
RUN npm install 


# Run - 2nd docker file
FROM node:20.18.3-alpine3.21
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/backend && \
    chown -R expense:expense /opt/backend
ENV DB_HOST="mysql"
USER expense

WORKDIR /opt/backend
COPY --from=build /opt/backend /opt/backend
CMD ["node", "index.js"]