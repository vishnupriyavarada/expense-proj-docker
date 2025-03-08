# IC-1
FROM node:20.18.3-alpine3.21
# # On top of IC-1, instruction 2 is executed, save this layer as image 2. IC-1 is deleted
# RUN addgroup -S expense && adduser -S expense -G expense 
# # Create IC#2. on top of IC-2, instruction 3 is executed , save this layer as image 3. IC-2 is deleted
# RUN mkdir /opt/backend
# RUN chown -R expense:expense /opt/backend

# Layers optimization. Multiple RUN instruction layers can be run as single instruction so that multiple/3 layers are reduced to 1 layer
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/backend && \
    chown -R expense:expense /opt/backend

WORKDIR /opt/backend

COPY package.json .
COPY *.js ./

RUN npm install 

ENV DB_HOST="mysql"

USER expense

CMD ["node", "index.js"]