# Use NodeJS base image
FROM node:13

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install -g @angular/cli
RUN npm install

# Install ionic
RUN npm install -g ionic

# Copy source
COPY . .

# Build the project
RUN ionic build

# Bind the port that the image will run on
EXPOSE 8100

# Define the Docker image's behavior at runtime
CMD ["ng","run","app:serve","--host=0.0.0.0","--port=8100","--disable-host-check"]
