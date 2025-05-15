# Base image - this project is using node 18
FROM node:18 

# Create app directory
WORKDIR /app/server

# A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY /server/package*.json ./package*.json

# Install app dependencies
RUN npm install

# Bundle app source
COPY ./server ./

# Creates a "dist" folder with the  build 
RUN npm run build

# Start the server using the  build
CMD [ "node", "dist/main.js" ]
