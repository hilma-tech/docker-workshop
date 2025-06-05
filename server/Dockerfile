# Base image - this project is using node 18
FROM node:18 

# Create app directory
WORKDIR /app/server

# Set environment variables for the database connection
# Replace with your actual database credentials or suitable defaults for development
ENV DB_USERNAME=your_user \
    DB_PASSWORD=your_password \
    DB_DBNAME=your_dbname \
    DB_HOST=db \
    DB_PORT=3306 \
    DB_ENGINE=mysql 
    # Add other necessary environment variables here, e.g., for TypeORM logging/sync
    # ENV TYPEORM_LOGGING=on \
    #     TYPEORM_SYNC=on

# A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY server/package.json ./

# Install app dependencies
RUN npm install

# Bundle app source
COPY server/ ./

# Creates a "dist" folder with the build 
RUN npm run build

# Start the server using the build
CMD [ "node", "dist/main.js" ]