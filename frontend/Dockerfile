# Use official Node.js image
FROM node:20-alpine

# Set working directory inside container
WORKDIR /app

# Copy package.json and package-lock.json / yarn.lock
COPY package*.json ./

# Install dependencies
RUN npm install -g vue-cli-service
RUN npm install

# Copy project files
COPY . .

# Build the app
RUN npm run build

# Use a lightweight web server to serve the app
RUN npm install -g serve

# Expose the port that the app will run on
EXPOSE 80

# Command to run the app
CMD ["serve", "-s", "dist", "-l", "80"]

