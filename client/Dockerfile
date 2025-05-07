FROM node:18 AS builder


WORKDIR /app/client

# Copy package.json and package-lock.json
COPY ./client/package.json /package.json

# Install dependencies
RUN --mount=type=cache,id=npm,target=/npm/store npm install  --frozen-lockfile

COPY ./client/ ./


RUN npm run build

# Stage 2: Serve React app with Nginx
FROM nginx:alpine

# Remove default Nginx website
RUN rm -rf /usr/share/nginx/html/*
RUN rm /etc/nginx/conf.d/default.conf;
COPY ./nginx /etc/nginx

# Copy build files from the 'builder' stage to Nginx server directory
COPY --from=builder /app/client/dist /usr/share/nginx/html
COPY --from=builder /app/client/ /app/client


# Copy nginx configuration file
EXPOSE 80
#
# Command to run Nginx
CMD ["nginx", "-g", "daemon off;"]