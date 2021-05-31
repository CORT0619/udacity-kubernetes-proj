# Use NodeJS base image
FROM beevelop/ionic AS ionic

# Create app directory in Docker
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./

# install ionic 
# RUN npm install -g ionic

# Install dependencies in Docker
# RUN npm install
RUN npm ci

# Copy app from local environment into the Docker image
COPY . .

# Set the API’s port number
# EXPOSE 8100
RUN ionic build

## Run 
FROM nginx:alpine
#COPY www /usr/share/nginx/html
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html


# RUN ionic build
# ENTRYPOINT [ "ionic" ]

# Define Docker’s behavior when the image is run
# CMD [ "serve", "--host", "0.0.0.0", " --port", "8100" ]