FROM node:18-alpine As development

# Create app directory
WORKDIR /usr/src/app

# Copying this first prevents re-running npm install on every code change.
COPY  package*.json ./

RUN npm ci


###################
# BUILD FOR PRODUCTION
###################

FROM node:18-alpine As build

WORKDIR /usr/src/app

COPY package*.json ./

# In order to run `npm run build` we need access to the Nest CLI which is a dev dependency. In the previous development stage we ran `npm ci` which installed all dependencies, so we can copy over the node_modules directory from the development image
COPY  --from=development /usr/src/app/node_modules ./node_modules

COPY  . .

# Run the build command which creates the production bundle
RUN npm run build

# Set NODE_ENV environment variable
ENV NODE_ENV development

RUN npm ci --omit=dev

###################
# PRODUCTION
###################

FROM node:18-alpine As production

WORKDIR /app
# Copy the bundled code from the build stage to the production image
COPY .env.development .env.development
COPY  --from=build /usr/src/app/node_modules node_modules
COPY  --from=build /usr/src/app/dist dist

ENV NODE_ENV development
# Start the server using the production build
CMD [ "node", "dist/main.js" ]

